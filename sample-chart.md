---
layout: article
title: "Sample Post Style Guide"
categories: articles
modified: 2014-08-27T11:57:41-04:00
tags: [sample]
---

Below a sample chart

<html>
	<head>
		<title>smoothed line | amCharts</title>
		<meta name="description" content="chart created using amCharts live editor" />

		<!-- amCharts javascript sources -->
		<script type="text/javascript" src="http://www.souliss.net/js/chart/amcharts.js"></script>
		<script type="text/javascript" src="http://www.souliss.net/js/chart/serial.js"></script>
		<script type="text/javascript" src="http://www.souliss.net/js/chart/patterns.js"></script>

		<!-- amCharts javascript code -->
		<script type="text/javascript">
			AmCharts.makeChart("chartdiv",
				{
					"type": "serial",
					"categoryField": "category",
					"autoMarginOffset": 40,
					"marginRight": 60,
					"marginTop": 60,
					"startDuration": 1,
					"fontSize": 13,
					"theme": "patterns",
					"categoryAxis": {
						"gridPosition": "start"
					},
					"trendLines": [],
					"graphs": [
						{
							"balloonText": "[[title]] of [[category]]:[[value]]",
							"bullet": "round",
							"bulletSize": 10,
							"id": "AmGraph-1",
							"lineAlpha": 1,
							"lineThickness": 3,
							"title": "graph 1",
							"type": "smoothedLine",
							"valueField": "column-1"
						}
					],
					"guides": [],
					"valueAxes": [
						{
							"id": "ValueAxis-1",
							"title": ""
						}
					],
					"allLabels": [],
					"balloon": {},
					"titles": [],
					"dataProvider": [
						{
							"category": "category 1",
							"column-1": 8,
							"column-2": 5
						},
						{
							"category": "category 2",
							"column-1": 6,
							"column-2": 7
						},
						{
							"category": "category 3",
							"column-1": 2,
							"column-2": 3
						},
						{
							"category": "category 4",
							"column-1": 1,
							"column-2": 3
						},
						{
							"category": "category 5",
							"column-1": 2,
							"column-2": 1
						},
						{
							"category": "category 6",
							"column-1": 3,
							"column-2": 2
						},
						{
							"category": "category 7",
							"column-1": 6,
							"column-2": 8
						}
					]
				}
			);
		</script>
	</head>
	<body>
		<div id="chartdiv" style="width: 100%; height: 400px; background-color: #FFFFFF;" ></div>
	</body>
</html>
