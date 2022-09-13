<template>
	<div ref="nvd3"></div>
</template>

<script>
import { getCurrentInstance, onMounted} from 'vue';
import d3 from 'd3';
import nv from 'nvd3';

export default {
	props: {
        options: {
            type: Object
        },
		data: {
			type: Array
		}
    },
	setup() {
		const { proxy } = getCurrentInstance();
		onMounted(() => {
			proxy.el = proxy.$refs.nvd3;
			if (proxy.options) {
				if (!proxy.chart || proxy.chartType !== proxy.options.chart.type) {
					proxy.initChart(proxy.options);
				} else {
					proxy.updateWithOptions(proxy.options);
				}
			}
		});
		return {
		}
	},
	data() {
		return {
			el: null,
			chart: {},
			chartType: "",
			svg: null,
        }
	},
	mounted() {
	},
	computed: {
    },
	methods: {
		initChart(options) {
			// Clearing
			this.clearElement();

			if (!options) {
				return;
			}

			// Initialize chart with specific type
			this.chart = nv.models[options.chart.type]();
			this.chartType = this.options.chart.type;

			// Generate random chart ID
			this.chart.id = Math.random().toString(36).substr(2, 15);

			this.updateWithOptions(options);

			nv.addGraph(() => {
			if (!this.chart) {
				return;
			}

			// Remove resize handler. Due to async execution should be placed here, not in the clearElement
			if (this.chart.resizeHandler) this.chart.resizeHandler.clear();

			// Update the chart when window resizes
			this.chart.resizeHandler = nv.utils.windowResize(() => {
				this.chart && this.chart.update && this.chart.update();
			});

			return this.chart;
			}, options.chart['callback']);
		},

		/**
		 * Update chart with new options.
		 * @param options
		 */
		updateWithOptions(options) {
			// Exit if options are not yet bound
			if (!options) {
				return;
			}

			for (let key in this.chart) {
			// if (!this.chart.hasOwnProperty(key)) continue;

			// let value = this.chart[key];

			if (key[0] === '_') { 
				console.log(1);
			} else if ([
				'clearHighlights',
				'highlightPoint',
				'id',
				'options',
				'resizeHandler',
				'state',
				'open',
				'close',
				'tooltipContent'
			].indexOf(key) >= 0) { 
				console.log(1);
			} else if (key === 'dispatch') {
				this.configureEvents(this.chart[key], options.chart[key]);
			} else if ([
				'bars',
				'bars1',
				'bars2',
				'boxplot',
				'bullet',
				'controls',
				'discretebar',
				'distX',
				'distY',
				'interactiveLayer',
				'legend',
				'lines',
				'lines1',
				'lines2',
				'multibar',
				'pie',
				'scatter',
				'scatters1',
				'scatters2',
				'sparkline',
				'stack1',
				'stack2',
				'sunburst',
				'tooltip',
				'x2Axis',
				'xAxis',
				'y1Axis',
				'y2Axis',
				'y3Axis',
				'y4Axis',
				'yAxis',
				'yAxis1',
				'yAxis2',
				'sankeyChart'
			].indexOf(key) >= 0 ||
				// stacked is a component for stackedAreaChart, but a boolean for multiBarChart and multiBarHorizontalChart
				(key === 'stacked' && options.chart.type === 'stackedAreaChart')) {
				this.configure(this.chart[key], options.chart[key], options.chart.type);
			}

			//TODO: need to fix bug in nvd3
			else if ((key === 'xTickFormat' || key === 'yTickFormat') && options.chart.type === 'lineWithFocusChart') {
				console.log(1);
			} else if ((key === 'tooltips') && options.chart.type === 'boxPlotChart') {
				console.log(1);
			} else if ((key === 'tooltipXContent' || key === 'tooltipYContent') && options.chart.type === 'scatterChart') {
				console.log(1);
			} else if (options.chart[key] === undefined || options.chart[key] === null) {
				console.log(1);
			} else {
				this.chart[key](options.chart[key]);
			}
			}

			this.updateWithData(this.data);
		},

		/**
		 * Update chart with new data.
		 * @param data
		 */
		updateWithData(data) {
			if (data) {

			// Select the add <svg> element (create it if necessary) and to render the chart in
			{
				let svgElement = this.el.querySelector('svg');
				if (!svgElement) {
					this.svg = d3.select(this.el).append('svg');
				} else {
					this.svg = d3.select(svgElement);
				}
			}

			this.updateSize();
			this.svg.datum(data).call(this.chart);
			}
		},

		/**
		 * Update the chart size.
		 */
		updateSize() {
			if (this.svg) {
				let h, w;
				h = this.options.chart.height;
				w = this.options.chart.width;
				if (h) {
					if (!isNaN(+h)) h += 'px';
					this.svg.attr('height', h).style({ height: h });
				}
				if (w) {
					if (!isNaN(+w)) w += 'px';
					this.svg.attr('width', w).style({ width: w });
				} else {
					this.svg.attr('width', '100%').style({ width: '100%' });
				}
			}
		},

		/**
		 * Synchronize the options with the options of the nvd3 chart.
		 * @param chart
		 * @param options
		 * @param chartType
		 */
		configure(chart, options, chartType) {
			if (chart && options) {
				for (let key in chart) {
					// if (!chart.hasOwnProperty(key)) continue;

					let value = chart[key];

					if (key[0] === '_') {
						console.log(1);
					}
					else if (key === 'dispatch') this.configureEvents(value, options[key]);
					else if (key === 'tooltip') this.configure(chart[key], options[key], chartType);
					else if (key === 'contentGenerator') {
					if (options[key]) chart[key](options[key]);
					}
					else if ([
					'axis',
					'clearHighlights',
					'defined',
					'highlightPoint',
					'nvPointerEventsClass',
					'options',
					'rangeBand',
					'rangeBands',
					'scatter',
					'open',
					'close'
					].indexOf(key) === -1) {
						if (options[key] === undefined || options[key] === null) {
							console.log(11);
						}
						else {
							chart[key](options[key]);
						}
					}
				}

			}
		},

		/**
		 * Configure dispatch events.
		 * @param dispatch
		 * @param options
		 */
		configureEvents(dispatch, options) {
			if (dispatch && options) {
			for (let key in dispatch) {
				// if (!dispatch.hasOwnProperty(key)) continue;

				if (options[key] === undefined || options[key] === null) {
					console.log(11);
				}
				else dispatch.on(key + '._', options[key]);
			}
			}
		},
		/**
		 * Cleanup an element.
		 */
		clearElement() {
			this.el.innerHTML = '';

			// remove tooltip if exists
			if (this.chart && this.chart.tooltip && this.chart.tooltip.id) {
			d3.select('#' + this.chart.tooltip.id()).remove();
			}

			// To be compatible with old nvd3 (v1.7.1)
			if (nv['graphs'] && this.chart) {
				for (var i = nv['graphs'].length - 1; i >= 0; i--) {
					if (nv['graphs'][i] && (nv['graphs'][i].id === this.chart.id)) {
					nv['graphs'].splice(i, 1);
					}
				}
			}
			if (nv.tooltip && nv.tooltip.cleanup) {
				nv.tooltip.cleanup();
			}
			if (this.chart && this.chart.resizeHandler) {
				this.chart.resizeHandler.clear();
			}
			this.chart = null;
		},
	},
	components: {
    }
}
</script>
<style scoped lang="scss">
	
</style>