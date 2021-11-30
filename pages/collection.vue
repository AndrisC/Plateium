<template>
  <div class="container">
    <div class="filter-container">
      <div class="filter-title">
        <h4>Filter</h4>
      </div>

      <div class="filter">
        <plt-select
          v-for="i in 5"
          :show-labels="false"
          :options="filterOptions"
          track-by="id"
          v-model="filterBy[i]"
          title="One filter"
          label="name"
          placeholder="placeholder text"
        />

        <plt-checkbox label="Checkbox title"/>
      </div>
    </div>

    <div class="product-container">
      <div class="search-area">
        <div class="title">
          <h3>All categories</h3>
        </div>

        <div class="search-container">
          <plt-input placeholder="Search..." />

          <plt-select
            :show-labels="false"
            :options="sortOptions"
            track-by="id"
            v-model="sortBy"
            label="name"
            placeholder="Sort by"
            class="plt-select"
          />
        </div>
      </div>

      <div class="product-area">
        <div v-for="product in products" class="one-product">
          <plt-product :product="product"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      sortOptions: [
        {name: 'Price descending', id: 0},
        {name: 'Price acsending', id: 1},
        {name: 'Name A-Z', id: 2},
        {name: 'Popularity', id: 3},
        {name: 'Newest first', id: 4},
      ],
      filterOptions: [
        {name: 'filter option 1', id: 0},
        {name: 'filter option 2', id: 1},
        {name: 'filter option 3', id: 2},
        {name: 'filter option 4', id: 3},
        {name: 'filter option 5', id: 4},
      ],
      sortBy: {},
      filterBy: [],
      products: [
        {
          _id: '9727475',
          name: 'Leaves',
          artist: 'Alexey Demidov',
          img: 'images/pexels-alexey-demidov-9727475-min.jpg',
          price: '$19.99'
        },
        {
          _id: '9727475',
          name: 'Abandoned ship',
          artist: 'Alina k',
          img: 'images/pexels-vyacheslav-bobin-9751579-min.jpg',
          price: '$19.99'
        },
        {
          _id: '9727475',
          name: 'Foresty beach',
          artist: 'Alina k',
          img: 'images/pexels-skyler-sion-9881700-min.jpg',
          price: '$19.99'
        },
        {
          _id: '9727475',
          name: 'Car lines',
          artist: 'Alina k',
          img: 'images/pexels-alina-k-9866828-min.jpg',
          price: '$19.99'
        },
        {
          _id: '9727475',
          name: 'Amusement park',
          artist: 'Alyssa Rose',
          img: 'images/pexels-alyssa-rose-9395308-min.jpg',
          price: '$19.99'
        },
        {
          _id: '9727475',
          name: 'Snowy mountains',
          artist: 'Anastasia R',
          img: 'images/pexels-anastasia-r-9904154-min.jpg',
          price: '$19.99'
        },
        {
          _id: '9727475',
          name: 'Sunrise at the barn',
          artist: 'Andrew Scharman',
          img: 'images/pexels-andrew-scharman-9702010-min.jpg',
          price: '$19.99'
        },
        {
          _id: '9727475',
          name: 'Fern',
          artist: 'Anna',
          img: 'images/pexels-anna-3972650-min.jpg',
          price: '$19.99'
        },
        {
          _id: '9727475',
          name: 'City from below',
          artist: 'Anna Kozlova',
          img: 'images/pexels-anna-kozlova-10162708-min.jpg',
          price: '$19.99'
        },
        {
          _id: '9727475',
          name: 'City from below',
          artist: 'Anna Kozlova',
          img: 'images/pexels-anna-rye-9092469-min.jpg',
          price: '$19.99'
        },
        {
          _id: '9727475',
          name: 'City from below',
          artist: 'Anna Kozlova',
          img: 'images/pexels-yaroslav-chaadaev-9654126-min.jpg',
          price: '$19.99'
        },
        {
          _id: '9727475',
          name: 'City from below',
          artist: 'Anna Kozlova',
          img: 'images/pexels-yew-hui-tan-9038269-min.jpg',
          price: '$19.99'
        },
        {
          _id: '9727475',
          name: 'City from below',
          artist: 'Anna Kozlova',
          img: 'images/pexels-yew-hui-tan-9038606-min.jpg',
          price: '$19.99'
        },
        {
          _id: '9727475',
          name: 'City from below',
          artist: 'Anna Kozlova',
          img: 'images/pexels-zhuravleva-anastasia-9985770-min.jpg',
          price: '$19.99'
        },
        {
          _id: '9727475',
          name: 'City from below',
          artist: 'Anna Kozlova',
          img: 'images/pexels-артём-н-9733511-min.jpg',
          price: '$19.99'
        },
      ]
    }
  },
}
</script>

<style lang="scss" scoped>
.container {
  padding: $space-m;
  display: flex;
  justify-content: center;
}
.filter-container {
  padding: $space-s;
  border-radius: $radius-default;
  box-shadow: $box-shadow;
  width: 280px;
  height: 540px;
}
.product-container {
  width: 80%;
  max-width: 1300px;
  margin-top: -$space-s;
  padding-left: $space-l;
}
.search-area {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
}
.search-container {
  display: flex;
  align-items: flex-end;
}
.plt-select {
  width: 200px;
  margin: 0 0 0 $space-s;
}
.product-area {
  margin-top: $space-l;
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  grid-auto-rows: auto;
  grid-gap: $space-l $space-m;
}
.one-product {
}
</style>
