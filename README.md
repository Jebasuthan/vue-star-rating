# VueJS Star Rating
Star Rating custom component using Pure VueJS application without any external package.

## Project setup
```
npm install
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
<td>maxStars</td>
<td>Number</td>
<td>Required.</td>
<td>Default value is <code>5</code>.</td>
</tr>
<tr>
<td>hasResults</td>
<td>Boolean</td>
<td>Optional.</td>
<td>Displaying the result values. Default value is <code>true</code>.</td>
</tr>
<tr>
<td>hasDescription</td>
<td>Boolean</td>
<td>Optional.</td>
<td>Default value is <code>true</code>.</td>
</tr>
<tr>
<td>ratingDescription</td>
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
<td>starSize</td>
<td>String</td>
<td>Optional.</td>
<td>Displaying the size of the stars. Default value is <code>lg</code>. We have <code>lg | xs | 6x</code> other optional values too.</td>
</tr>
<tr>
</tbody>
</table>

# Usage

Step 1: import and use the custom Rating component.

```
import Rating from './components/Rating'
```
Step 2: Import the Rating component inside the App component
```
<script>

import Rating from './components/Rating'

export default {
  name: 'app',
  components: {
    Rating
  }
}
</script>
```
Step 3: Load defalt values to the component
```
data() {
    return {
      desc: [
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
      starSize: 'lg' //xs/6x
    }
}
```

Step 4: Place the Rate component inside the template
```
<template>
  <div id="app">
    <Rating :star="2" :starSize="starSize" :hasResults="true" :hasDescription="true" :ratingDescription="desc" />
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

### Run your tests
```
npm run test
```
