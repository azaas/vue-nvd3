# nvd3

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

mian.js import style
import 'nvd3/build/nv.d3.css';

App.vue import VueNvd3 component
import VueNvd3 from './components/VueNvd3.vue';

Register in the components of app.vue
components: {
    VueNvd3
  }
  
<VueNvd3 :options="pieChartOptions" :data="pieChartData"></VueNvd3>

Example
Let's create a simple Pie Chart.

Configure options:
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
}
