let Fred = require('fred-api');
let googleFinance = require('google-finance');

apiKey ="996a0a9dd2aef2811c4929a6fc4fe628";
fred = new Fred(apiKey);

//Baseline Data
//GDP Q4 2007 = 100
let baselineGDP = 14681.501;
//Wilshire 5000 Total Market Index Q4 2007 = 100
let baselineWilshire = 55.05;
//Wilshire Index Multiplier
let wilshireIndexMultiplier = 220.5;
//Current Data
let currentGDP;
let currentWilshire;
let current2Year;
let current10Year;
let currentTreasurySpread;
let currentBitcoin;
let currentEtherum;

fred.getSeriesObservations({series_id: 'WILL5000INDFC'},function(error, result){
	let string = JSON.stringify(result);
	currentWilshire = string.slice(string.length-10,string.length-4);
	let nominalWilshire = wilshireIndexMultiplier * parseFloat(currentWilshire);
	//console.log(wilshireIndexMultiplier*parseFloat(currentWilshire));


fred.getSeriesObservations({series_id:'GDP'},function(error,result){
	let string = JSON.stringify(result);
	currentGDP = string.slice(string.length-13,string.length-4);
	console.log("Warren Buffett Ratio(Wilshire5000/GDP(Nominal)) = "+nominalWilshire/parseFloat(currentGDP));
    });

    });

fred.getSeriesObservations({series_id:'DGS2'},function(error,result){
	let string = JSON.stringify(result);
	current2Year = string.slice(string.length-8,string.length-4);
	console.log("2 Year Treasury Yield Spread(Monthly) = "+current2Year);
});

fred.getSeriesObservations({series_id:'GS10'},function(error,result){
	let string = JSON.stringify(result);
	current10Year = string.slice(string.length-8, string.length-4);
	console.log("10-Year Treaury Yield(Monthly) = "+current10Year);
});

//Daily Updated 10year - 2 year Yield Constant Maturity
fred.getSeriesObservations({series_id:'T10Y2Y'},function(error,result){
	let string = JSON.stringify(result);
	currentTreasurySpread = string.slice(string.length-8, string.length-4);
	console.log("10-2 Year Treasury Yield Spread(Daily) = "+currentTreasurySpread);
});

//Bitcoin Price
fred.getSeriesObservations({series_id:'CBBTCUSD'},function(error,result){
	let string = JSON.stringify(result);
	currentBitcoin = string.slice(string.length-10, string.length-4);
	console.log("Bitcoin Price(Daily) = "+currentBitcoin);
});

//Etherum Price
fred.getSeriesObservations({series_id:'CBETHUSD'},function(error,result){
	let string = JSON.stringify(result);
	currentEtherum = string.slice(string.length-10, string.length-4);
	console.log("Etherum Price(Daily) = "+currentEtherum);
});