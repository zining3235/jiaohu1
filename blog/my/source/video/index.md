---
title: 拉雅与最后的龙（预告片）
date: 2021-04-03 21:20:41
---
<center>拉雅与最后的龙（预告片）</center>
<div id="dplayer"></div>
<script src="/js/DPlayer.min.js"></script>
<script>
const dp = new DPlayer({
    container: document.getElementById('dplayer'),
    screenshot: true,
    video: {
        url: 'https://cdn.jsdelivr.net/gh/zining3235/hexo-DIY@main/yan-ge-zhi-ye.mp4',
        pic: 'https://amo-1252276119.cos.ap-shanghai.myqcloud.com/video/cs.jpg',
        thumbnails: 'thumbnails.jpg',
    },
    subtitle: {
        url: 'webvtt.vtt',
    },
    danmaku: {
        id: 'demo',
        api: 'https://api.prprpr.me/dplayer/',
    },
});
</script>