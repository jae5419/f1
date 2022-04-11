<template>
    <div id="news">
        <div>
            <img :src="article.img" alt="2022 F1">
            <p>{{ article.main }}</p>
        </div>
        <a :href="article.src">자세히 보기</a>
    </div>
</template>

<script>
export default {
    name: 'NewsContainer',
    data: function() {
        return {
            article: {img: require('../assets/saudiGP.jpg'), main: "레드불과 페라리가 선두 경쟁을 펼치고 있는 가운데", src: "https://www.motorgraph.com/news/articleView.html?idxno=29591"}
        }
    }
}
</script>