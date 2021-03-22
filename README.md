# VueJS Star Rating
Awesome Vue Star Rating using Pure VueJS application without any external package.

## Installing
```
npm install --save awesome-vue-star-rating
```

## Options
 
 <table>
<thead>
<tr>
<th>Property</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>star</td>
<td>Number</td>
<td>Required.</td>
<td>Default value of Star. Default value is <code>2</code></td>
</tr>
<tr>
<td>maxstars</td>
<td>Number</td>
<td>Required.</td>
<td>Default value is <code>5</code>.</td>
</tr>
<tr>
<td>hasresults</td>
<td>Boolean</td>
<td>Optional.</td>
<td>Displaying the result values. Default value is <code>true</code>.</td>
</tr>
<tr>
<td>hasdescription</td>
<td>Boolean</td>
<td>Optional.</td>
<td>Default value is <code>true</code>.</td>
</tr>
<tr>
<td>ratingdescription</td>
<td>Array</td>
<td>Required.</td>
<td>Displaying the rating values. Ex. <code>[{
          text: 'Poor',
          class: 'star-poor'
        },
        {
          text: 'Below Average',
          class: 'star-belowAverage'
        },
        {
          text: 'Average',
          class: 'star-average'
        },
        {
          text: 'Good',
          class: 'star-good'
        },
        {
          text: 'Excellent',
          class: 'star-excellent'
        }]</code></td>
</tr>
<tr>
<td>starsize</td>
<td>String</td>
<td>Optional.</td>
<td>Displaying the size of the stars. Default value is <code>lg</code>. We have <code>lg | xs | 6x</code> other optional values too.</td>
</tr>
<tr>
</tbody>
</table>

# Usage

Step 1: import AwesomeVueStarRating in our component

```
import AwesomeVueStarRating from 'awesome-vue-star-rating'

export default {
  name: 'app',
  components: {
    AwesomeVueStarRating
  }
}
</script>
```
Step 2: Load default values to the component

```
data() {
    return {
      star: 5, // default star
      ratingdescription: [
        {
          text: 'Poor',
          class: 'star-poor'
        },
        {
          text: 'Below Average',
          class: 'star-belowAverage'
        },
        {
          text: 'Average',
          class: 'star-average'
        },
        {
          text: 'Good',
          class: 'star-good'
        },
        {
          text: 'Excellent',
          class: 'star-excellent'
        }
      ],
      hasresults: true,
      hasdescription: true,
      starsize: 'lg' //xs/6x
    }
}
```

Step 3: Place the Rate component inside the template
```
<template>
  <div id="app">
    <AwesomeVueStarRating :star="this.star" :starsize="this.starsize" :hasresults="this.hasresults" :hasdescription="this.hasdescription" :ratingdescription="this.ratingdescription" />
  </div>
</template>
```



### Compiles and hot-reloads for development
```
npm run serve
```

# Screen Shot
<img width="343" alt="Screenshot 2021-03-15 at 9 56 04 PM" src="https://user-images.githubusercontent.com/3702438/111186769-5aa39700-85d9-11eb-9708-e68fda77524d.png">


# Demo
![Vue_Star](https://user-images.githubusercontent.com/3702438/111186905-7b6bec80-85d9-11eb-9b53-a11aaf422c5b.gif)

### Compiles and minifies for production
```
npm run build
```
# Live DEMO
[Live DEMO](https://codesandbox.io/s/reverent-heyrovsky-juycp)
### Run your tests
```
npm run test
```
