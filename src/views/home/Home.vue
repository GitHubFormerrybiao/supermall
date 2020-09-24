<template>
  <div id="home">
    <nav-bar class="home-nav">
      <div slot="center">购物街</div>
    </nav-bar>
    <home-swiper :banners="banners"></home-swiper>
    <recommend-view :recommends="recommends"></recommend-view>
    <feature-view></feature-view>
    <tab-control class="tab-control" :titles="['流行', '新款', '精选']" />
    <ul>
      <li>数据1</li>
      <li>数据2</li>
      <li>数据3</li>
      <li>数据4</li>
      <li>数据5</li>
      <li>数据6</li>
      <li>数据7</li>
      <li>数据8</li>
      <li>数据9</li>
      <li>数据10</li>
      <li>数据11</li>
      <li>数据12</li>
      <li>数据13</li>
      <li>数据14</li>
      <li>数据15</li>
      <li>数据16</li>
      <li>数据17</li>
      <li>数据18</li>
      <li>数据19</li>
      <li>数据20</li>
      <li>数据21</li>
      <li>数据22</li>
      <li>数据23</li>
      <li>数据24</li>
      <li>数据25</li>
      <li>数据26</li>
      <li>数据27</li>
      <li>数据28</li>
      <li>数据29</li>
      <li>数据30</li>
      <li>数据31</li>
      <li>数据32</li>
      <li>数据33</li>
      <li>数据34</li>
      <li>数据35</li>
      <li>数据36</li>
      <li>数据37</li>
      <li>数据38</li>
      <li>数据39</li>
      <li>数据40</li>
      <li>数据41</li>
      <li>数据42</li>
      <li>数据43</li>
      <li>数据44</li>
      <li>数据45</li>
      <li>数据46</li>
      <li>数据47</li>
      <li>数据48</li>
      <li>数据49</li>
      <li>数据50</li>
      <li>数据51</li>
      <li>数据52</li>
      <li>数据53</li>
      <li>数据54</li>
      <li>数据55</li>
      <li>数据56</li>
      <li>数据57</li>
      <li>数据58</li>
      <li>数据59</li>
      <li>数据60</li>
      <li>数据61</li>
      <li>数据62</li>
      <li>数据63</li>
      <li>数据64</li>
      <li>数据65</li>
      <li>数据66</li>
      <li>数据67</li>
      <li>数据68</li>
      <li>数据69</li>
      <li>数据70</li>
      <li>数据71</li>
      <li>数据72</li>
      <li>数据73</li>
      <li>数据74</li>
      <li>数据75</li>
      <li>数据76</li>
      <li>数据77</li>
      <li>数据78</li>
      <li>数据79</li>
      <li>数据80</li>
      <li>数据81</li>
      <li>数据82</li>
      <li>数据83</li>
      <li>数据84</li>
      <li>数据85</li>
      <li>数据86</li>
      <li>数据87</li>
      <li>数据88</li>
      <li>数据89</li>
      <li>数据90</li>
      <li>数据91</li>
      <li>数据92</li>
      <li>数据93</li>
      <li>数据94</li>
      <li>数据95</li>
      <li>数据96</li>
      <li>数据97</li>
      <li>数据98</li>
      <li>数据99</li>
      <li>数据100</li>
    </ul>
  </div>
</template>

<script>
import NavBar from "components/common/navbar/NavBar";
import HomeSwiper from "./childComps/HomeSwiper";
import RecommendView from "./childComps/RecommendView";
import FeatureView from "./childComps/FeatureView";

import TabControl from "components/content/tabControl/TabControl";

import { getHomeMultidata, getHomeGoods } from "network/home";

export default {
  name: "Home",
  components: {
    NavBar,
    HomeSwiper,
    RecommendView,
    FeatureView,
    TabControl,
  },
  data() {
    return {
      banners: [],
      recommends: [],
      goods: {
        pop: { page: 0, list: [] },
        new: { page: 0, list: [] },
        sell: { page: 0, list: [] },
      },
    };
  },
  created() {
    this.getHomeMultidata();
    // 2.请求商品数据
    this.getHomeGoods("pop");
    this.getHomeGoods("new");
    this.getHomeGoods("sell");
  },
  methods: {
    getHomeMultidata() {
      getHomeMultidata().then((res) => {
        this.banners = res.data.banner.list;
        this.recommends = res.data.recommend.list;
      });
    },
    getHomeGoods(type) {
      const page = this.goods[type].page + 1;
      getHomeGoods(type, page).then((res) => {
        this.goods[type].list.push(...res.data.list);
        this.goods[type].page += 1;
      });
    },
  },
};
</script>

<style scoped>
#home {
  /*padding-top: 44px;*/
  padding-top: 44px;
}

.home-nav {
  background-color: var(--color-tint);
  color: #fff;

  position: fixed;
  left: 0;
  right: 0;
  top: 0;
  z-index: 9;
}

.tab-control {
  position: sticky;
  top: 44px;
}
</style>
