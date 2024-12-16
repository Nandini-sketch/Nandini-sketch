-module.exports = {
  webpack: {
    configure: (webpackConfig) => {
      const sourceMapLoader = webpackConfig.module.rules.find(
        (rule) => rule.enforce === 'pre' && rule.use && rule.use.some((loader) => loader.loader.includes('source-map-loader'))
      );

      if (sourceMapLoader) {
        sourceMapLoader.exclude = [
          /node_modules\/ag-grid-community/,
          /node_modules\/ag-grid-react/,
        ];
      }

      return webpackConfig;
    },
  },
};

<!---
Nandini-sketch/Nandini-sketch is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
