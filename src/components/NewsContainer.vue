<template>
    <div id="news">
        <div>
            <img :src="article.img" alt="2022 F1">
            <h3>{{ article.headline }}</h3>
            <p>{{ article.main }}</p>
        </div>
        <a :href="article.src" target="_blank">자세히 보기</a>
    </div>
</template>

<script>
export default {
    name: 'NewsContainer',
    data: function() {
        return {
            article: {img: require('../assets/AustGP.jpg'), headline: "[주간F1] '파죽지세' 르클레르, 폴투윈 우승…레드불 신뢰도 문제 어쩌나",
            main: "지난 10일(현지시간) 열린 2022 포뮬러 원(F1) 월드챔피언십 3라운드에서 스쿠데리아 페라리 소속 샤를 르클레르가 예선과 본선 모두 1위를 차지하는 폴투윈을 거뒀다. 르클레르는 3회 경기 중 2회 우승하며 챔피언십 선두를 굳히고 있다. 이번 경기는 호주 멜버른에 위치한 앨버트파크 서킷에서 진행됐다. 코로나19 여파로 취소된 이후 3년 만에 열린 행사다. 결승전 당일에만 호주 그랑프리 사상 최다 관중인 약 42만명이 앨버트 파크를 찾는 등 대성황을 이뤘다. 르클레르는 예선전에서 디펜딩 챔피언 맥스 페르스타펜(레드불 레이싱)을 누르고 폴 포지션에 올랐다. 본선에서도 초반부터 경쟁자들과 큰 격차를 벌린 르클레르는 모든 랩을 리드하며 안정적인 우승을 거뒀다. 여기에 패스티스트 랩까지 더해져 총 26점을 획득한 르클레르는 누적 71점으로 2위 조지 러셀(37점)과 큰 격차를 벌이고 있다. 반면 팀 메이트 카를로스 사인스 주니어에겐 운이 따르지 않았다. 예선전 100% 컨디션을 발휘하지 못한 사인스는 예선 9위로 마무리하며 힘겨운 결선 스타트를 치렀다. 이어 경기 초반 상위권으로 치고나가기 위해 페이스를 끌어올리던 도중, 다소 무리한 코너 진입으로 자갈밭에 빠지며 단 3랩만에 경기를 종료했다.",
            src: "https://www.motorgraph.com/news/articleView.html?idxno=29718"}
        }
    }
}
</script>

<style>
#news {
    width: 62%;
    background-color: beige;
    padding: 20px;
}

#news>div {
    overflow: hidden;
    text-overflow: ellipsis;
    display: -webkit-box;
    -webkit-line-clamp: 9;
    -webkit-box-orient: vertical;
}

#news>div img {
    width: 240px;
    height: 160px;
    float: left;
}

#news>div p {
    font-size: 14px;
}

#news a {
    float: right;
    font-size: 15px;
    text-decoration: none;
    color: white;
    background-color: mediumseagreen;
    border-radius: 12px;
    padding: 2px 6px;
}

#news a:hover {
    background-color: cornflowerblue;
}
</style>