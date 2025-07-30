<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Stacked Area Chart - ArcGIS + Plotly</title>
    <script src="https://cdn.plot.ly/plotly-latest.min.js"></script>
</head>
<body>
    <div id="chart" style="width: 100%; height: 600px;"></div>

    <script>
        // --- 1. Get URL parameters from Experience Builder ---
        function getUrlParams() {
            const params = {};
            window.location.search.replace(/[?&]+([^=&]+)=([^&]*)/gi, function(str, key, value) {
                params[key] = decodeURIComponent(value);
            });
            return params;
        }

        const urlParams = getUrlParams();
        const segment = urlParams.segment || 'Main Lake'; // Default if none provided

        // --- 2. Build ArcGIS REST Query ---
        const serviceUrl = "https://services.arcgis.com/pwNwIGBE7M7VOXjQ/arcgis/rest/services/LCB_Implementation_Model_Cumulative_Table/FeatureServer/0/query";
        const where = `lakesegment='${segment}'`; // filter by segment
        const queryUrl = `${serviceUrl}?where=${encodeURIComponent(where)}&outFields=*&f=json`;

        // --- 3. Fetch data ---
        fetch(queryUrl)
            .then(response => response.json())
            .then(data => {
                if (!data.features || data.features.length === 0) {
                    document.getElementById('chart').innerHTML = '<p>No data found.</p>';
                    return;
                }

                // --- 4. Transform: Extract attributes and pivot for Plotly ---
                const attributes = data.features[0].attributes;

                // Extract all year fields (yr_2010 ... yr_2036)
                const years = Object.keys(attributes)
                    .filter(key => key.startsWith('yr_'))
                    .map(key => key.replace('yr_', ''))
                    .sort();

                const values = years.map(y => attributes[`yr_${y}`]);

                // --- 5. Build stacked area chart ---
                const trace = {
                    x: years,
                    y: values,
                    type: 'scatter',
                    mode: 'lines',
                    fill: 'tonexty',
                    name: segment
                };

                const layout = {
                    title: `Implementation Model Cumulative - ${segment}`,
                    xaxis: { title: 'Year' },
                    yaxis: { title: 'Value' },
                    showlegend: true
                };

                Plotly.newPlot('chart', [trace], layout);
            })
            .catch(error => {
                console.error('Error fetching data:', error);
                document.getElementById('chart').innerHTML = '<p>Error loading data.</p>';
            });
    </script>
</body>
</html>