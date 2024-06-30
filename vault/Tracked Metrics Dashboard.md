
## Life Design
---

```dataviewjs

dv.span("**Life Design Log**")

const pages = dv.pages('"Monthly"').sort(p => p.file.day.toISODate())

const dates = pages.filter(p => 
	(p.health_fitness_life_rating != undefined) || 
	(p.intellectual_life_rating != undefined) || 
	(p.emotional_life_rating != undefined) || 
	(p.character_life_rating != undefined) || 
	(p.spiritual_life_rating != undefined) ||
	(p.love_relationships_life_rating != undefined) ||
	(p.parenting_life_rating != undefined) ||
	(p.social_life_rating != undefined) ||
	(p.financial_life_rating != undefined) ||
	(p.career_life_rating != undefined) ||
	(p.quality_of_life_rating != undefined) ||
	(p.life_vision_rating != undefined)
	).map(p => p.file.day.toISODate())

const health_fitness_life_rating = pages.filter(p => p.health_fitness_life_rating != undefined).map(p => p.health_fitness_life_rating).values
const intellectual_life_rating = pages.filter(p => p.intellectual_life_rating != undefined).map(p => p.intellectual_life_rating).values
const emotional_life_rating = pages.filter(p => p.emotional_life_rating != undefined).map(p => p.emotional_life_rating).values
const character_life_rating = pages.filter(p => p.character_life_rating != undefined).map(p => p.character_life_rating).values
const spiritual_life_rating = pages.filter(p => p.spiritual_life_rating != undefined).map(p => p.spiritual_life_rating).values
const love_relationships_life_rating = pages.filter(p => p.love_relationships_life_rating != undefined).map(p => p.love_relationships_life_rating).values
const parenting_life_rating = pages.filter(p => p.parenting_life_rating != undefined).map(p => p.parenting_life_rating).values
const social_life_rating = pages.filter(p => p.social_life_rating != undefined).map(p => p.social_life_rating).values
const financial_life_rating = pages.filter(p => p.financial_life_rating != undefined).map(p => p.financial_life_rating).values
const career_life_rating = pages.filter(p => p.career_life_rating != undefined).map(p => p.career_life_rating).values
const quality_of_life_rating = pages.filter(p => p.quality_of_life_rating != undefined).map(p => p.quality_of_life_rating).values
const life_vision_rating = pages.filter(p => p.life_vision_rating != undefined).map(p => p.life_vision_rating).values

const chartData = {
	type: 'bar',
	beginAtZero: 0,
	data: {
		labels: dates,
		datasets: [
		{
			label: 'Health and Fitness Life', 
			data: health_fitness_life_rating, 
			backgroundColor: [
				'rgba(200, 150, 150, 1)'
			], 
			borderColor: [
				'rgba(138, 102, 204, 0.8)'
			], 
			borderWidth: 1.5, 
			spanGaps: true,
		},
		{
			label: 'Intellectual Life', 
			data: intellectual_life_rating, 
			backgroundColor: [
				'rgba(10, 255, 50, 1)'
			], 
			borderColor: [
				'rgba(138, 102, 204, 0.8)'
			], 
			borderWidth: 1.5, 
			spanGaps: true,
		},
		{
			label: 'Emotional Life', 
			data: emotional_life_rating, 
			backgroundColor: [
				'rgba(50, 255, 50, 1)'
			], 
			borderColor: [
				'rgba(138, 102, 204, 0.8)'
			], 
			borderWidth: 1.5, 
			spanGaps: true,
		},
		{
			label: 'Character Life', 
			data: character_life_rating, 
			backgroundColor: [
				'rgba(255, 50, 255, 1)'
			], 
			borderColor: [
				'rgba(138, 102, 204, 0.8)'
			], 
			borderWidth: 1.5, 
			spanGaps: true,
		},
		{
			label: 'Spiritual Life', 
			data: spiritual_life_rating, 
			backgroundColor: [
				'rgba(255, 255, 50, 1)'
			], 
			borderColor: [
				'rgba(138, 102, 204, 0.8)'
			], 
			borderWidth: 1.5, 
			spanGaps: true,
		},
		{
			label: 'Love Relationship Life', 
			data: love_relationships_life_rating, 
			backgroundColor: [
				'rgba(50, 255, 255, 1)'
			], 
			borderColor: [
				'rgba(50, 50, 150, 0.8)'
			], 
			borderWidth: 1.5, 
			spanGaps: true,
		},
		{
			label: 'Parenting Life', 
			data: parenting_life_rating, 
			backgroundColor: [
				'rgba(100, 200, 255, 1)'
			], 
			borderColor: [
				'rgba(138, 102, 204, 0.8)'
			], 
			borderWidth: 1.5, 
			spanGaps: true,
		},
		{
			label: 'Social Life', 
			data: social_life_rating, 
			backgroundColor: [
				'rgba(30, 20, 255, 2)'
			], 
			borderColor: [
				'rgba(138, 102, 204, 0.8)'
			], 
			borderWidth: 1.5, 
			spanGaps: true,
		},
		{
			label: 'Financial Life', 
			data: financial_life_rating, 
			backgroundColor: [
				'rgba(40, 50, 30, 1)'
			], 
			borderColor: [
				'rgba(138, 102, 204, 0.8)'
			], 
			borderWidth: 1.5, 
			spanGaps: true,
		},
		{
			label: 'Career Life', 
			data: career_life_rating, 
			backgroundColor: [
				'rgba(20, 10, 5, 1)'
			], 
			borderColor: [
				'rgba(138, 102, 204, 0.8)'
			], 
			borderWidth: 1.5, 
			spanGaps: true,
		},
		{
			label: 'Quality of Life', 
			data: quality_of_life_rating, 
			backgroundColor: [
				'rgba(20, 255, 40, 10)'
			], 
			borderColor: [
				'rgba(138, 102, 204, 0.8)'
			], 
			borderWidth: 1.5, 
			spanGaps: true,
		},
		{
			label: 'Life Vision', 
			data: life_vision_rating, 
			backgroundColor: [
				'rgba(200, 50, 50, 1)'
			], 
			borderColor: [
				'rgba(138, 102, 204, 0.8)'
			], 
			borderWidth: 1.5, 
			spanGaps: true,
		}
		],
	},
};

window.renderChart(chartData, this.container)

```
```dataviewjs

dv.span("**Day Rating Log**")

const pages = dv.pages('"Daily"').sort(p => p.file.day.toISODate())

const dates = pages.filter(p => p["day_self_rating"] != undefined).map(p => p.file.day.toISODate())

const day_rating = pages.filter(p => p["day_self_rating"] != undefined).map(p => p["day_self_rating"]).values


const chartData = {
	type: 'line',
	data: {
		beginAtZero: true,
		labels: dates,
		datasets: [
		{
			label: 'Day Rating', 
			data: day_rating, 
			backgroundColor: [
				'rgba(53, 252, 167, 1)'
			], 
			borderColor: [
				'rgba(138, 102, 204, 0.8)'
			], 
			borderWidth: 1.5, 
			spanGaps: true,
		}
		],
	},
};

window.renderChart(chartData, this.container)

```

```dataviewjs

const pages = dv.pages()
    .where(page => page.type === "daily" || page.type === "daily_tracker");

dv.table(["Day", "Day Self-Rating", "Daily Summary", "Daily Lowlights", "Daily Highlights"], 
    pages.filter(p => 
	(p["day_self-rating"] != undefined) || 
	(p["daily-summary"] != undefined) || 
	(p["daily-lowlights"] != undefined) || 
	(p["daily-highlights"] != undefined)
	).slice(-3).map(page => [
	    dv.fileLink(page.file.path),
        page["day_self_rating"],
        page["daily-summary"],
        page["daily-lowlights"],
        page["daily-highlights"]
    ])
);
```

## Health 
---

```dataviewjs

dv.span("**Weight Log**")

const pages = dv.pages('"Daily"').sort(p => p.file.day.toISODate())

const dates = pages.filter(p => p.weight != undefined).map(p => p.file.day.toISODate())

const weights = pages.filter(p => p.weight != undefined).map(p => p.weight).values


const chartData = {
	type: 'line',
	data: {
		labels: dates,
		datasets: [
		{
			label: 'Weight (lbs)', 
			data: weights, 
			backgroundColor: [
				'rgba(53, 252, 167, 1)'
			], 
			borderColor: [
				'rgba(138, 102, 204, 0.8)'
			], 
			borderWidth: 1.5, 
			spanGaps: true,
		}
		],
	},
};

window.renderChart(chartData, this.container)

```
```dataviewjs

dv.span("**BFP and Vfat Log**")

const pages = dv.pages('"Daily"').sort(p => p.file.day.toISODate())

const dates = pages.map(p => p.file.day.toISODate())

const bfp = pages.map(p => p.inbody_bfp).values
const vfat = pages.map(p => p.inbody_vfat).values

const chartData = {
	type: 'line',
	data: {
		labels: dates,
		datasets: [
		{
			label: 'BFP (%)', 
			data: bfp, 
			backgroundColor: [
				'rgba(53, 100, 100, 100)'
			], 
			borderColor: [
				'rgba(138, 102, 204, 0.8)'
			], 
			borderWidth: 1.5, 
			spanGaps: true,
		},
		{
			label: 'VFAT (%)', 
			data: vfat, 
			backgroundColor: [
				'rgba(53, 50, 50, 50)'
			], 
			borderColor: [
				'rgba(138, 102, 204, 0.8)'
			], 
			borderWidth: 1.5, 
			spanGaps: true,
		}
		],
	},
};

window.renderChart(chartData, this.container)

```

## Activity 
---

```dataviewjs

dv.span("**Sleep Log**")

const pages = dv.pages('"Daily"').sort(p => p.file.day.toISODate())

const dates = pages.filter(p => p.sleep_hrs != undefined).map(p => p.file.day.toISODate())

const sleep_hrs = pages.filter(p => p.sleep_hrs != undefined).map(p => p.sleep_hrs).values


const chartData = {
	type: 'line',
	data: {
		labels: dates,
		datasets: [
		{
			label: 'Sleep (hrs)', 
			data: sleep_hrs, 
			backgroundColor: [
				'rgba(53, 252, 167, 1)'
			], 
			borderColor: [
				'rgba(138, 102, 204, 0.8)'
			], 
			borderWidth: 1.5, 
			spanGaps: true,
		}
		],
	},
};

window.renderChart(chartData, this.container)

```

```dataviewjs

dv.span("**HR Log**")

const pages = dv.pages('"Daily"').sort(p => p.file.day.toISODate())

const dates = pages.filter(p => p.hr_max != undefined).map(p => p.file.day.toISODate())

const hr_max = pages.filter(p => p.hr_max != undefined).map(p => p.hr_max).values

const chartData = {
	type: 'line',
	data: {
		labels: dates,
		datasets: [
		{
			label: 'HR Max (bpm)', 
			data: hr_max, 
			backgroundColor: [
				'rgba(53, 252, 167, 1)'
			], 
			borderColor: [
				'rgba(138, 102, 204, 0.8)'
			], 
			borderWidth: 1.5, 
			spanGaps: true,
		}
		],
	},
};

window.renderChart(chartData, this.container)

```

```dataviewjs

dv.span("**Exercise Log (mins)**")

const pages = dv.pages('"Daily"').sort(p => p.file.day.toISODate())

const dates = pages.map(p => p.file.day.toISODate())

const strength_training_mins = pages.map(p => p.strength_training_mins).values
const biked_mins = pages.map(p => p.biked_mins).values

const chartData = {
	type: 'line',
	data: {
		labels: dates,
		datasets: [
		{
			label: 'Strength Training (mins)', 
			data: strength_training_mins, 
			backgroundColor: [
				'rgba(255, 100, 100, 1)'
			], 
			borderColor: [
				'rgba(138, 102, 204, 0.8)'
			], 
			borderWidth: 1.5, 
			spanGaps: true,
		},
		{
			label: 'Biked (mins)', 
			data: biked_mins, 
			backgroundColor: [
				'rgba(53, 50, 50, 50)'
			], 
			borderColor: [
				'rgba(138, 102, 204, 0.8)'
			], 
			borderWidth: 1.5, 
			spanGaps: true,
		}
		],
	},
};

window.renderChart(chartData, this.container)

```
```dataviewjs

dv.span("**Strength Training - Reps Log**")

const pages = dv.pages('"Daily"').sort(p => p.file.day.toISODate())

const dates = pages.filter(p => p.strength_training_reps != undefined).map(p => p.file.day.toISODate())

const strength_training_reps = pages.filter(p => p.strength_training_reps != undefined).map(p => p.strength_training_reps).values

const chartData = {
	type: 'line',
	data: {
		labels: dates,
		datasets: [
		{
			label: 'Reps', 
			data: strength_training_reps, 
			backgroundColor: [
				'rgba(53, 252, 167, 1)'
			], 
			borderColor: [
				'rgba(138, 102, 204, 0.8)'
			], 
			borderWidth: 1.5, 
			spanGaps: true,
		}
		],
	},
};

window.renderChart(chartData, this.container)

```
```dataviewjs

dv.span("**Bike Log (miles)**")

const pages = dv.pages('"Daily"').sort(p => p.file.day.toISODate())

const dates = pages.filter(p => p.biked_miles != undefined).map(p => p.file.day.toISODate())

const biked_miles = pages.filter(p => p.biked_miles != undefined).map(p => p.biked_miles).values

const chartData = {
	type: 'line',
	data: {
		labels: dates,
		datasets: [
		{
			label: 'Biked (miles)', 
			data: biked_miles, 
			backgroundColor: [
				'rgba(53, 252, 167, 1)'
			], 
			borderColor: [
				'rgba(138, 102, 204, 0.8)'
			], 
			borderWidth: 1.5, 
			spanGaps: true,
		}
		],
	},
};

window.renderChart(chartData, this.container)

```
```dataviewjs

dv.span("**Bike Log (minutes)**")

const pages = dv.pages('"Daily"').sort(p => p.file.day.toISODate())

const dates = pages.filter(p => p.biked_mins != undefined).map(p => p.file.day.toISODate())

const biked_mins = pages.filter(p => p.biked_mins != undefined).map(p => p.biked_mins).values

const chartData = {
	type: 'line',
	data: {
		labels: dates,
		datasets: [
		{
			label: 'Biked (mins)', 
			data: biked_mins, 
			backgroundColor: [
				'rgba(53, 252, 167, 1)'
			], 
			borderColor: [
				'rgba(138, 102, 204, 0.8)'
			], 
			borderWidth: 1.5, 
			spanGaps: true,
		}
		],
	},
};

window.renderChart(chartData, this.container)

```
```dataviewjs

dv.span("**Zones Log (mins)**")

const pages = dv.pages('"Daily"').sort(p => p.file.day.toISODate())

const dates = pages.filter(p => (p.zone1_mins != undefined) || (p.zone2_mins != undefined) || (p.zone3_mins != undefined) || (p.zone4_mins != undefined) || (p.zone5_mins != undefined)).map(p => p.file.day.toISODate())

const zone1_mins = pages.filter(p => p.zone1_mins != undefined).map(p => p.zone1_mins).values
const zone2_mins = pages.filter(p => p.zone2_mins != undefined).map(p => p.zone2_mins).values
const zone3_mins = pages.filter(p => p.zone3_mins != undefined).map(p => p.zone3_mins).values
const zone4_mins = pages.filter(p => p.zone4_mins != undefined).map(p => p.zone4_mins).values
const zone5_mins = pages.filter(p => p.zone5_mins != undefined).map(p => p.zone5_mins).values

const chartData = {
	type: 'bar',
	stacked: true,
	data: {
		labels: dates,
		datasets: [
		{
			label: 'Zone 1 (mins)', 
			data: zone1_mins, 
			backgroundColor: [
				'rgba(0, 0, 0, 2)'
			], 
			borderColor: [
				'rgba(138, 102, 204, 0.8)'
			], 
			borderWidth: 1.5, 
			spanGaps: true,
		},
		{
			label: 'Zone 2 (mins)', 
			data: zone2_mins, 
			backgroundColor: [
				'rgba(0, 200, 255, 9)'
			], 
			borderColor: [
				'rgba(138, 102, 204, 0.8)'
			], 
			borderWidth: 1.5, 
			spanGaps: true,
		},
		{
			label: 'Zone 3 (mins)', 
			data: zone3_mins, 
			backgroundColor: [
				'rgba(0, 255, 50, 5)'
			], 
			borderColor: [
				'rgba(138, 102, 204, 0.8)'
			], 
			borderWidth: 1.5, 
			spanGaps: true,
		},
		{
			label: 'Zone 4 (mins)', 
			data: zone4_mins, 
			backgroundColor: [
				'rgba(255, 255, 50, 5)'
			], 
			borderColor: [
				'rgba(138, 102, 204, 0.8)'
			], 
			borderWidth: 1.5, 
			spanGaps: true,
		}
		,
		{
			label: 'Zone 5 (mins)', 
			data: zone5_mins, 
			backgroundColor: [
				'rgba(255, 0, 50, 1)'
			], 
			borderColor: [
				'rgba(138, 102, 204, 0.8)'
			], 
			borderWidth: 1.5, 
			spanGaps: true,
		}
		],
	},
};

window.renderChart(chartData, this.container)

```