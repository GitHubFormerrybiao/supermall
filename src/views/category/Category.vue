<template>
  <div class="wrapper">
    <ul class="content">
      <button @click="click">按钮</button>
      <li>元素标签1</li>
      <li>元素标签2</li>
      <li>元素标签3</li>
      <li>元素标签4</li>
      <li>元素标签5</li>
      <li>元素标签6</li>
      <li>元素标签7</li>
      <li>元素标签8</li>
      <li>元素标签9</li>
      <li>元素标签10</li>
      <li>元素标签11</li>
      <li>元素标签12</li>
      <li>元素标签13</li>
      <li>元素标签14</li>
      <li>元素标签15</li>
      <li>元素标签16</li>
      <li>元素标签17</li>
      <li>元素标签18</li>
      <li>元素标签19</li>
      <li>元素标签20</li>
      <li>元素标签21</li>
      <li>元素标签22</li>
      <li>元素标签23</li>
      <li>元素标签24</li>
      <li>元素标签25</li>
      <li>元素标签26</li>
      <li>元素标签27</li>
      <li>元素标签28</li>
      <li>元素标签29</li>
      <li>元素标签30</li>
      <li>元素标签31</li>
      <li>元素标签32</li>
      <li>元素标签33</li>
      <li>元素标签34</li>
      <li>元素标签35</li>
      <li>元素标签36</li>
      <li>元素标签37</li>
      <li>元素标签38</li>
      <li>元素标签39</li>
      <li>元素标签40</li>
      <li>元素标签41</li>
      <li>元素标签42</li>
      <li>元素标签43</li>
      <li>元素标签44</li>
      <li>元素标签45</li>
      <li>元素标签46</li>
      <li>元素标签47</li>
      <li>元素标签48</li>
      <li>元素标签49</li>
      <li>元素标签50</li>
      <li>元素标签51</li>
      <li>元素标签52</li>
      <li>元素标签53</li>
      <li>元素标签54</li>
      <li>元素标签55</li>
      <li>元素标签56</li>
      <li>元素标签57</li>
      <li>元素标签58</li>
      <li>元素标签59</li>
      <li>元素标签60</li>
      <li>元素标签61</li>
      <li>元素标签62</li>
      <li>元素标签63</li>
      <li>元素标签64</li>
      <li>元素标签65</li>
      <li>元素标签66</li>
      <li>元素标签67</li>
      <li>元素标签68</li>
      <li>元素标签69</li>
      <li>元素标签70</li>
      <li>元素标签71</li>
      <li>元素标签72</li>
      <li>元素标签73</li>
      <li>元素标签74</li>
      <li>元素标签75</li>
      <li>元素标签76</li>
      <li>元素标签77</li>
      <li>元素标签78</li>
      <li>元素标签79</li>
      <li>元素标签80</li>
      <li>元素标签81</li>
      <li>元素标签82</li>
      <li>元素标签83</li>
      <li>元素标签84</li>
      <li>元素标签85</li>
      <li>元素标签86</li>
      <li>元素标签87</li>
      <li>元素标签88</li>
      <li>元素标签89</li>
      <li>元素标签90</li>
      <li>元素标签91</li>
      <li>元素标签92</li>
      <li>元素标签93</li>
      <li>元素标签94</li>
      <li>元素标签95</li>
      <li>元素标签96</li>
      <li>元素标签97</li>
      <li>元素标签98</li>
      <li>元素标签99</li>
      <li>元素标签100</li>
    </ul>
  </div>
</template>

<script>
import BScroll from "better-scroll";
export default {
  name: "Category",
  data() {
    return {
      scroll: null,
    };
  },
  mounted() {
    // new BScroll(".content", {});
    this.scroll = new BScroll(document.querySelector(".wrapper"), {
      probeType: 3,
      pullUpLoad: true,
    });
    this.scroll.on("scroll", (position) => {
      console.log(position);
    });
    this.scroll.on("pullingUp", () => {
      console.log("上拉加载更多");
    });
  },
  methods: {
    click() {
      console.log("发生了点击");
    },
  },
};
</script>

<style scoped>
.wrapper {
  height: 150px;
  background-color: red;
  overflow: hidden;
}
</style>
