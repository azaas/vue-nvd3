<template>
  <h1>Line Chart</h1>
  <VueNvd3 :options="lineChartOptions" :data="lineChartData"></VueNvd3>
  <h1>Pie Chart</h1>
  <VueNvd3 :options="pieChartOptions" :data="pieChartData"></VueNvd3>
  <h1>Discrete Bar Chart</h1>
  <VueNvd3 :options="discreteBarChartOptions" :data="discreteBarChartData"></VueNvd3>
  <h1>Multi Bar Chart</h1>
  <VueNvd3 :options="multiBarChartOptions" :data="multiBarChartData"></VueNvd3>
  <h1>Multi Bar Horizontal Chart</h1>
  <VueNvd3 :options="multiBarHorizontalChartOptions" :data="multiBarHorizontalChartData"></VueNvd3>
  <h1>Stacked Area Chart</h1>
  <VueNvd3 :options="stackedAreaChartOptions" :data="stackedAreaChartData"></VueNvd3>
</template>


<script>
import VueNvd3 from './components/VueNvd3.vue'
import d3 from 'd3';
export default {
  name: 'App',
  components: {
    VueNvd3
  },
  data() {
    return {
      lineChartData: [{"values":[{"x":0,"y":0},{"x":1,"y":0.09983341664682815},{"x":2,"y":0.19866933079506122},{"x":3,"y":0.29552020666133955},{"x":4,"y":0.3894183423086505},{"x":5,"y":0.479425538604203},{"x":6,"y":0.5646424733950354},{"x":7,"y":0.644217687237691},{"x":8,"y":0.7173560908995228},{"x":9,"y":0.7833269096274834},{"x":10,"y":0.8414709848078965},{"x":11,"y":0.8912073600614354},{"x":12,"y":0.9320390859672263},{"x":13,"y":0.963558185417193},{"x":14,"y":0.9854497299884601},{"x":15,"y":0.9974949866040544},{"x":16,"y":0.9995736030415051},{"x":17,"y":0.9916648104524686},{"x":18,"y":0.9738476308781951},{"x":19,"y":0.9463000876874145},{"x":20,"y":0.9092974268256817},{"x":21,"y":0.8632093666488737},{"x":22,"y":0.8084964038195901},{"x":23,"y":0.7457052121767203},{"x":24,"y":0.675463180551151},{"x":25,"y":0.5984721441039564},{"x":26,"y":0.5155013718214642},{"x":27,"y":0.4273798802338298},{"x":28,"y":0.3349881501559051},{"x":29,"y":0.23924932921398243},{"x":30,"y":0.1411200080598672},{"x":31,"y":0.04158066243329049},{"x":32,"y":-0.058374143427580086},{"x":33,"y":-0.1577456941432482},{"x":34,"y":-0.2555411020268312},{"x":35,"y":-0.35078322768961984},{"x":36,"y":-0.44252044329485246},{"x":37,"y":-0.5298361409084934},{"x":38,"y":-0.6118578909427189},{"x":39,"y":-0.6877661591839738},{"x":40,"y":-0.7568024953079282},{"x":41,"y":-0.8182771110644103},{"x":42,"y":-0.8715757724135882},{"x":43,"y":-0.9161659367494549},{"x":44,"y":-0.9516020738895161},{"x":45,"y":-0.977530117665097},{"x":46,"y":-0.9936910036334644},{"x":47,"y":-0.9999232575641008},{"x":48,"y":-0.9961646088358407},{"x":49,"y":-0.9824526126243325},{"x":50,"y":-0.9589242746631385},{"x":51,"y":-0.9258146823277325},{"x":52,"y":-0.8834546557201531},{"x":53,"y":-0.8322674422239013},{"x":54,"y":-0.7727644875559871},{"x":55,"y":-0.7055403255703919},{"x":56,"y":-0.6312666378723216},{"x":57,"y":-0.5506855425976376},{"x":58,"y":-0.46460217941375737},{"x":59,"y":-0.373876664830236},{"x":60,"y":-0.27941549819892586},{"x":61,"y":-0.18216250427209588},{"x":62,"y":-0.0830894028174964},{"x":63,"y":0.016813900484349713},{"x":64,"y":0.11654920485049364},{"x":65,"y":0.21511998808781552},{"x":66,"y":0.31154136351337786},{"x":67,"y":0.4048499206165983},{"x":68,"y":0.49411335113860816},{"x":69,"y":0.5784397643882002},{"x":70,"y":0.6569865987187891},{"x":71,"y":0.7289690401258759},{"x":72,"y":0.7936678638491532},{"x":73,"y":0.8504366206285644},{"x":74,"y":0.8987080958116269},{"x":75,"y":0.9379999767747389},{"x":76,"y":0.9679196720314863},{"x":77,"y":0.9881682338770004},{"x":78,"y":0.998543345374605},{"x":79,"y":0.998941341839772},{"x":80,"y":0.9893582466233818},{"x":81,"y":0.9698898108450863},{"x":82,"y":0.9407305566797731},{"x":83,"y":0.9021718337562934},{"x":84,"y":0.8545989080882805},{"x":85,"y":0.7984871126234903},{"x":86,"y":0.7343970978741134},{"x":87,"y":0.6629692300821833},{"x":88,"y":0.5849171928917617},{"x":89,"y":0.5010208564578846},{"x":90,"y":0.4121184852417566},{"x":91,"y":0.3190983623493521},{"x":92,"y":0.22288991410024764},{"x":93,"y":0.1244544235070617},{"x":94,"y":0.024775425453357765},{"x":95,"y":-0.0751511204618093},{"x":96,"y":-0.17432678122297965},{"x":97,"y":-0.27176062641094245},{"x":98,"y":-0.3664791292519284},{"x":99,"y":-0.4575358937753214}],"key":"Sine Wave","color":"#ff7f0e","strokeWidth":2,"classed":"dashed"},{"values":[{"x":0,"y":-0.1248153203950875},{"x":1,"y":-0.22326918962858935},{"x":2,"y":-0.2902295627107948},{"x":3,"y":-0.2958308182821921},{"x":4,"y":-0.3052966015313575},{"x":5,"y":-0.33064088111952705},{"x":6,"y":-0.37431753455795014},{"x":7,"y":-0.41042857993775717},{"x":8,"y":-0.39280332524502765},{"x":9,"y":-0.38744114417109804},{"x":10,"y":-0.4166768897097867},{"x":11,"y":-0.41977868769279714},{"x":12,"y":-0.45911739264789114},{"x":13,"y":-0.4571804585570436},{"x":14,"y":-0.39919597315674427},{"x":15,"y":-0.4589826545391171},{"x":16,"y":-0.37770511711186494},{"x":17,"y":-0.36753465355922693},{"x":18,"y":-0.32921169787879645},{"x":19,"y":-0.3236495889018037},{"x":20,"y":-0.22738171021900777},{"x":21,"y":-0.23849418020080157},{"x":22,"y":-0.2149589828603092},{"x":23,"y":-0.11421391704224365},{"x":24,"y":-0.12027658331026704},{"x":25,"y":-0.0795287829751074},{"x":26,"y":-0.011977762203648795},{"x":27,"y":-0.0014116163433889111},{"x":28,"y":0.09283613405258498},{"x":29,"y":0.1787945442297839},{"x":30,"y":0.19302224556756967},{"x":31,"y":0.24925870116133547},{"x":32,"y":0.27261074742174357},{"x":33,"y":0.3689029458798161},{"x":34,"y":0.3557707977327938},{"x":35,"y":0.428554927148097},{"x":36,"y":0.47935122104611433},{"x":37,"y":0.47327799295778805},{"x":38,"y":0.4977696112659823},{"x":39,"y":0.48280621909917376},{"x":40,"y":0.4957723774755904},{"x":41,"y":0.5172312235052597},{"x":42,"y":0.5872981736335876},{"x":43,"y":0.516878167575833},{"x":44,"y":0.5712891488365253},{"x":45,"y":0.5458415612803731},{"x":46,"y":0.4868463136051148},{"x":47,"y":0.5098639608230093},{"x":48,"y":0.5281647703739384},{"x":49,"y":0.45326449417363796},{"x":50,"y":0.4192217752453504},{"x":51,"y":0.38032679184311935},{"x":52,"y":0.32060423699713436},{"x":53,"y":0.27427887555286895},{"x":54,"y":0.28738821385390706},{"x":55,"y":0.2447410704850233},{"x":56,"y":0.19177480128348418},{"x":57,"y":0.13201140882276952},{"x":58,"y":0.03869531852833896},{"x":59,"y":-0.01736467334995885},{"x":60,"y":-0.0721885164243796},{"x":61,"y":-0.03034760102301863},{"x":62,"y":-0.08546011048890306},{"x":63,"y":-0.19687329782353602},{"x":64,"y":-0.20708713845157303},{"x":65,"y":-0.2580549215332123},{"x":66,"y":-0.2519755588449384},{"x":67,"y":-0.3238093972526004},{"x":68,"y":-0.3754277307321228},{"x":69,"y":-0.3379457158223299},{"x":70,"y":-0.4334171592149358},{"x":71,"y":-0.4046700070659996},{"x":72,"y":-0.41852816081672434},{"x":73,"y":-0.4546713840355038},{"x":74,"y":-0.3999379766360105},{"x":75,"y":-0.46679303486228596},{"x":76,"y":-0.453418985870696},{"x":77,"y":-0.44289898078225215},{"x":78,"y":-0.40754890175742486},{"x":79,"y":-0.4176551267336237},{"x":80,"y":-0.3949129199882934},{"x":81,"y":-0.3200003578905022},{"x":82,"y":-0.31229722286325506},{"x":83,"y":-0.24170556108536848},{"x":84,"y":-0.2019758904037586},{"x":85,"y":-0.21752203930157185},{"x":86,"y":-0.1417285999946263},{"x":87,"y":-0.08844231194219705},{"x":88,"y":-0.004505646832910007},{"x":89,"y":-0.000978780746368764},{"x":90,"y":0.05186752229232419},{"x":91,"y":0.11891769747504967},{"x":92,"y":0.12240649467334852},{"x":93,"y":0.185287352671254},{"x":94,"y":0.2788293944033653},{"x":95,"y":0.2819680543550648},{"x":96,"y":0.36280640552545407},{"x":97,"y":0.41308906589708216},{"x":98,"y":0.41379538688315465},{"x":99,"y":0.41888870072004436}],"key":"Cosine Wave","color":"#2ca02c"},{"values":[{"x":0,"y":0.5},{"x":1,"y":0.524958354161707},{"x":2,"y":0.5496673326987653},{"x":3,"y":0.5738800516653348},{"x":4,"y":0.5973545855771626},{"x":5,"y":null},{"x":6,"y":0.6411606183487588},{"x":7,"y":0.6610544218094228},{"x":8,"y":0.6793390227248807},{"x":9,"y":0.6958317274068708},{"x":10,"y":0.7103677462019742},{"x":11,"y":0.7228018400153589},{"x":12,"y":0.7330097714918066},{"x":13,"y":0.7408895463542983},{"x":14,"y":0.746362432497115},{"x":15,"y":null},{"x":16,"y":0.7498934007603762},{"x":17,"y":0.7479162026131172},{"x":18,"y":0.7434619077195488},{"x":19,"y":0.7365750219218536},{"x":20,"y":0.7273243567064205},{"x":21,"y":0.7158023416622185},{"x":22,"y":0.7021241009548975},{"x":23,"y":0.6864263030441801},{"x":24,"y":0.6688657951377878},{"x":25,"y":null},{"x":26,"y":0.6288753429553661},{"x":27,"y":0.6068449700584575},{"x":28,"y":0.5837470375389763},{"x":29,"y":0.5598123323034956},{"x":30,"y":0.5352800020149668},{"x":31,"y":0.5103951656083227},{"x":32,"y":0.48540646414310495},{"x":33,"y":0.46056357646418794},{"x":34,"y":0.4361147244932922},{"x":35,"y":null},{"x":36,"y":0.3893698891762869},{"x":37,"y":0.3675409647728767},{"x":38,"y":0.3470355272643203},{"x":39,"y":0.32805846020400653},{"x":40,"y":0.31079937617301795},{"x":41,"y":0.29543072223389744},{"x":42,"y":0.28210605689660295},{"x":43,"y":0.2709585158126363},{"x":44,"y":0.26209948152762097},{"x":45,"y":null},{"x":46,"y":0.2515772490916339},{"x":47,"y":0.2500191856089748},{"x":48,"y":0.25095884779103983},{"x":49,"y":0.2543868468439169},{"x":50,"y":0.26026893133421536},{"x":51,"y":0.2685463294180669},{"x":52,"y":0.2791363360699617},{"x":53,"y":0.29193313944402466},{"x":54,"y":0.3068088781110032},{"x":55,"y":null},{"x":56,"y":0.34218334053191957},{"x":57,"y":0.3623286143505906},{"x":58,"y":0.38384945514656066},{"x":59,"y":0.406530833792441},{"x":60,"y":0.43014612545026853},{"x":61,"y":0.45445937393197605},{"x":62,"y":0.4792276492956259},{"x":63,"y":0.5042034751210874},{"x":64,"y":0.5291373012126234},{"x":65,"y":null},{"x":66,"y":0.5778853408783444},{"x":67,"y":0.6012124801541496},{"x":68,"y":0.623528337784652},{"x":69,"y":0.64460994109705},{"x":70,"y":0.6642466496796973},{"x":71,"y":0.682242260031469},{"x":72,"y":0.6984169659622883},{"x":73,"y":0.7126091551571411},{"x":74,"y":0.7246770239529068},{"x":75,"y":null},{"x":76,"y":0.7419799180078716},{"x":77,"y":0.7470420584692501},{"x":78,"y":0.7496358363436513},{"x":79,"y":0.749735335459943},{"x":80,"y":0.7473395616558455},{"x":81,"y":0.7424724527112716},{"x":82,"y":0.7351826391699433},{"x":83,"y":0.7255429584390733},{"x":84,"y":0.7136497270220701},{"x":85,"y":null},{"x":86,"y":0.6835992744685284},{"x":87,"y":0.6657423075205459},{"x":88,"y":0.6462292982229404},{"x":89,"y":0.6252552141144712},{"x":90,"y":0.6030296213104391},{"x":91,"y":0.579774590587338},{"x":92,"y":0.555722478525062},{"x":93,"y":0.5311136058767654},{"x":94,"y":0.5061938563633395},{"x":95,"y":null},{"x":96,"y":0.4564183046942551},{"x":97,"y":0.4320598433972644},{"x":98,"y":0.40838021768701793},{"x":99,"y":0.38561602655616967}],"key":"Another sine wave","color":"#7777ff","area":true}],
			lineChartOptions: {
        "chart": {
          "type": "lineChart",
          "height": 450,
          "margin": {
            "top": 20,
            "right": 20,
            "bottom": 40,
            "left": 55
          },
          "useInteractiveGuideline": true,
          "dispatch": {},
          "xAxis": {
            "axisLabel": "Time (ms)",
            "dispatch": {},
            "axisLabelDistance": 0,
            "staggerLabels": false,
            "rotateLabels": 0,
            "rotateYLabel": true,
            "showMaxMin": true,
            "height": 60,
            "ticks": null,
            "width": 75,
            "margin": {
              "top": 0,
              "right": 0,
              "bottom": 0,
              "left": 0
            },
            "duration": 250,
            "orient": "bottom",
            "tickValues": null,
            "tickSubdivide": 0,
            "tickSize": 6,
            "tickPadding": 7,
            "domain": [
              0,
              1
            ],
            "range": [
              0,
              1
            ]
          },
          "yAxis": {
            "axisLabel": "Voltage (v)",
            "axisLabelDistance": -10,
            "dispatch": {},
            "staggerLabels": false,
            "rotateLabels": 0,
            "rotateYLabel": true,
            "showMaxMin": true,
            "height": 60,
            "ticks": null,
            "width": 75,
            "margin": {
              "top": 0,
              "right": 0,
              "bottom": 0,
              "left": 0
            },
            "duration": 250,
            "orient": "left",
            "tickValues": null,
            "tickSubdivide": 0,
            "tickSize": 6,
            "tickPadding": 3,
            "domain": [
              0,
              1
            ],
            "range": [
              0,
              1
            ]
          },
          "lines": {
            "dispatch": {},
            "width": 960,
            "height": 500,
            "xDomain": null,
            "yDomain": null,
            "pointDomain": [
              16,
              256
            ],
            "xRange": null,
            "yRange": null,
            "pointRange": null,
            "forceX": [],
            "forceY": [],
            "forcePoint": [],
            "interactive": true,
            "padDataOuter": 0.1,
            "padData": false,
            "clipEdge": true,
            "clipVoronoi": true,
            "showVoronoi": false,
            "id": 44688,
            "interactiveUpdateDelay": 300,
            "showLabels": false,
            "margin": {
              "top": 0,
              "right": 0,
              "bottom": 0,
              "left": 0
            },
            "duration": 0,
            "useVoronoi": true,
            "interpolate": "linear"
          },
          "lines2": {
            "dispatch": {},
            "width": 960,
            "height": 500,
            "xDomain": null,
            "yDomain": null,
            "pointDomain": [
              16,
              256
            ],
            "xRange": null,
            "yRange": null,
            "pointRange": null,
            "forceX": [],
            "forceY": [],
            "forcePoint": [],
            "interactive": false,
            "padDataOuter": 0.1,
            "padData": false,
            "clipEdge": false,
            "clipVoronoi": true,
            "showVoronoi": false,
            "id": 49630,
            "interactiveUpdateDelay": 300,
            "showLabels": false,
            "margin": {
              "top": 0,
              "right": 0,
              "bottom": 0,
              "left": 0
            },
            "duration": 250,
            "useVoronoi": true,
            "interpolate": "linear"
          },
          "legend": {
            "dispatch": {},
            "width": 400,
            "height": 20,
            "align": true,
            "maxKeyLength": 20,
            "rightAlign": true,
            "padding": 32,
            "updateState": true,
            "radioButtonMode": false,
            "expanded": false,
            "vers": "classic",
            "margin": {
              "top": 5,
              "right": 0,
              "bottom": 5,
              "left": 0
            }
          },
          "x2Axis": {
            "dispatch": {},
            "axisLabelDistance": 0,
            "staggerLabels": false,
            "rotateLabels": 0,
            "rotateYLabel": true,
            "showMaxMin": true,
            "axisLabel": null,
            "height": 60,
            "ticks": null,
            "width": 75,
            "margin": {
              "top": 0,
              "right": 0,
              "bottom": 0,
              "left": 0
            },
            "duration": 250,
            "orient": "bottom",
            "tickValues": null,
            "tickSubdivide": 0,
            "tickSize": 6,
            "tickPadding": 5,
            "domain": [
              0,
              1
            ],
            "range": [
              0,
              1
            ]
          },
          "y2Axis": {
            "dispatch": {},
            "axisLabelDistance": 0,
            "staggerLabels": false,
            "rotateLabels": 0,
            "rotateYLabel": true,
            "showMaxMin": true,
            "axisLabel": null,
            "height": 60,
            "ticks": null,
            "width": 75,
            "margin": {
              "top": 0,
              "right": 0,
              "bottom": 0,
              "left": 0
            },
            "duration": 250,
            "orient": "left",
            "tickValues": null,
            "tickSubdivide": 0,
            "tickSize": 6,
            "tickPadding": 3,
            "domain": [
              0,
              1
            ],
            "range": [
              0,
              1
            ]
          },
          "interactiveLayer": {
            "dispatch": {},
            "tooltip": {
              "duration": 0,
              "gravity": "w",
              "distance": 25,
              "snapDistance": 0,
              "classes": null,
              "chartContainer": null,
              "enabled": true,
              "hideDelay": 0,
              "headerEnabled": true,
              "fixedTop": null,
              "offset": {
                "left": 0,
                "top": 0
              },
              "hidden": false,
              "data": null,
              "id": "nvtooltip-22659"
            },
            "margin": {
              "left": 55,
              "top": 30
            },
            "width": null,
            "height": null,
            "showGuideLine": true,
            "svgContainer": null
          },
          "tooltip": {
            "duration": 100,
            "gravity": "w",
            "distance": 25,
            "snapDistance": 0,
            "classes": null,
            "chartContainer": null,
            "enabled": true,
            "hideDelay": 200,
            "headerEnabled": true,
            "fixedTop": null,
            "offset": {
              "left": 0,
              "top": 0
            },
            "hidden": true,
            "data": null,
            "id": "nvtooltip-88260"
          },
          "width": null,
          "interpolate": "linear",
          "clipEdge": true,
          "duration": 250,
          "clipVoronoi": true,
          "forcePoint": [],
          "forceX": [],
          "forceY": [],
          "interactive": true,
          "interactiveUpdateDelay": 300,
          "padData": false,
          "padDataOuter": 0.1,
          "pointDomain": [
            16,
            256
          ],
          "pointRange": null,
          "showLabels": false,
          "showVoronoi": false,
          "useVoronoi": true,
          "xDomain": null,
          "xRange": null,
          "yDomain": null,
          "yRange": null,
          "showLegend": true,
          "legendPosition": "top",
          "showXAxis": true,
          "showYAxis": true,
          "focusEnable": false,
          "focusShowAxisX": true,
          "focusShowAxisY": false,
          "brushExtent": null,
          "defaultState": null,
          "noData": null,
          "focusMargin": {
            "top": 0,
            "right": 20,
            "bottom": 20,
            "left": 60
          },
          "rightAlignYAxis": false
        },
        "title": {
          "enable": true,
          "text": "Title for Line Chart",
          "className": "h4",
          "css": {
            "width": "nullpx",
            "textAlign": "center"
          }
        },
        "subtitle": {
          "enable": true,
          "text": "Subtitle for simple line chart. Lorem ipsum dolor sit amet, at eam blandit sadipscing, vim adhuc sanctus disputando ex, cu usu affert alienum urbanitas.",
          "css": {
            "width": "nullpx",
            "textAlign": "center",
            "text-align": "center",
            "margin": "10px 13px 0px 7px"
          }
        },
        "caption": {
          "enable": true,
          "text": "Figure 1. Write Your Caption text.",
          "css": {
            "width": "nullpx",
            "textAlign": "center",
            "text-align": "justify",
            "margin": "10px 13px 0px 7px"
          },
          "html": "<b>Figure 1.</b> Lorem ipsum dolor sit amet, at eam blandit sadipscing, <span style=\"text-decoration: underline;\">vim adhuc sanctus disputando ex</span>, cu usu affert alienum urbanitas. <i>Cum in purto erat, mea ne nominavi persecuti reformidans.</i> Docendi blandit abhorreant ea has, minim tantas alterum pro eu. <span style=\"color: darkred;\">Exerci graeci ad vix, elit tacimates ea duo</span>. Id mel eruditi fuisset. Stet vidit patrioque in pro, eum ex veri verterem abhorreant, id unum oportere intellegam nec<sup>[1, <a href=\"https://github.com/krispo/angular-nvd3\" target=\"_blank\">2</a>, 3]</sup>."
        },
        "styles": {
          "classes": {
            "with-3d-shadow": true,
            "with-transitions": true,
            "gallery": false
          },
          "css": {}
        }
      },
      pieChartData: [
				{key: "One", y: 5},
				{key: "Two", y: 2}
			],
			pieChartOptions: {
				chart: {
				type: 'pieChart',
				height: 500,
				x: function (d) {
					return d.key;
				},
				y: function (d) {
					return d.y;
				}
				}
			},
      discreteBarChartOptions: {
        chart: {
          type: 'discreteBarChart',
          height: 450,
          x: function (d) {
            return d.label;
          },
          y: function (d) {
            return d.value;
          }
        }
      },
      discreteBarChartData: [
        {
          key: "Cumulative Return",
          values: [
            {"label": "A", "value": 10},
            {"label": "B", "value": 20}
          ]
        }
      ],
      multiBarChartOptions: {
        chart: {
          type: 'multiBarChart',
          height: 450,
          stacked: true
        }
      },
      multiBarChartData: [
        {
          key: 'Sent',
          values: [{x: 0, y: 1}, {x: 1, y: 2}]
        },
        {
          key: 'Received',
          values: [{x: 0, y: 2}, {x: 1, y: 3}]
        },
        {
          key: 'Spam',
          values: [{x: 0, y: 3}, {x: 1, y: 5}]
        }
      ],
      multiBarHorizontalChartOptions: {
        chart: {
          type: 'multiBarHorizontalChart',
          height: 450,
          x: function (d) {
            return d.label;
          },
          y: function (d) {
            return d.value;
          }
        }
      },
      multiBarHorizontalChartData: [
      {
        "key": "Series1",
        "values": [
          {
            "label": "Group A",
            "value": -1.8746444827653
          },
          {
            "label": "Group B",
            "value": -8.0961543492239
          }
        ]
      },
      {
        "key": "Series2",
        "values": [
          {
            "label": "Group A",
            "value": 25.307646510375
          },
          {
            "label": "Group B",
            "value": 16.756779544553
          }
        ]
      }
      ],
      stackedAreaChartOptions: {
        chart: {
            type: 'stackedAreaChart',
            height: 450,
            margin : {
                top: 20,
                right: 20,
                bottom: 30,
                left: 40
            },
            x: function(d){return d[0];},
            y: function(d){return d[1];},
            useVoronoi: false,
            clipEdge: true,
            duration: 100,
            useInteractiveGuideline: true,
            xAxis: {
                showMaxMin: false,
                tickFormat: function(d) {
                    return d3.time.format('%x')(new Date(d))
                }
            },
            yAxis: {
                tickFormat: function(d){
                    return d3.format(',.2f')(d);
                }
            },
            zoom: {
                enabled: true,
                scaleExtent: [1, 10],
                useFixedDomain: false,
                useNiceScale: false,
                horizontalOff: false,
                verticalOff: true,
                unzoomEventType: 'dblclick.zoom'
            }
        }
      },
      stackedAreaChartData: [
        {
          "key": "North America",
          "values": [[1025409600000, 23.041422681023], [1028088000000, 19.854291255832]]
        },
        {
          "key": "Africa",
          "values": [[1025409600000, 7.9356392949025], [1028088000000, 7.4514668527298]]
        }
      ],
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
