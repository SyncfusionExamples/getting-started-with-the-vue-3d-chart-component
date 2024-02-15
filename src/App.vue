<script setup>
import { Chart3DComponent as EjsChart3d, Chart3DSeriesCollectionDirective as EChart3dSeriesCollection, 
         Chart3DSeriesDirective as EChart3dSeries, ColumnSeries3D, Category3D, DataLabel3D,
         Legend3D, Tooltip3D } from "@syncfusion/ej2-vue-charts";
import { provide } from 'vue';
const primaryXAxis = {valueType: 'Category'};
const chart3d = [ColumnSeries3D, Category3D, DataLabel3D, Legend3D, Tooltip3D];
const title = "Sales Analysis";
const dataLabel = { visible : true };
const legendSettings = { visible: true };
const tooltip = { enable: true };
const seriesData = [
    { month: 'Jan', sales: 35 }, { month: 'Feb', sales: 28 },
    { month: 'Mar', sales: 34 }, { month: 'Apr', sales: 32 },
    { month: 'May', sales: 40 }, { month: 'Jun', sales: 32 },
    { month: 'Jul', sales: 35 }, { month: 'Aug', sales: 55 },
    { month: 'Sep', sales: 38 }, { month: 'Oct', sales: 30 },
    { month: 'Nov', sales: 25 }, { month: 'Dec', sales: 32 }
];
provide('chart3d', chart3d);
</script>

<template>
    <ejs-chart3d :primaryXAxis='primaryXAxis' :title="title" :legendSettings="legendSettings"
                 :tooltip="tooltip">
        <e-chart3d-series-collection>
            <e-chart3d-series type='Column' :dataSource='seriesData'  xName='month' yName='sales'
                             :dataLabel="dataLabel" name="Sales" > 
            </e-chart3d-series>
        </e-chart3d-series-collection>
    </ejs-chart3d>
</template>

<style scoped>
</style>