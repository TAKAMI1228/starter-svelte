<script type="ts">
    var today = new Date();

    var year = today.getFullYear();
    var month = today.getMonth()+1;
    var day = today.getDate();
    var week = today.getDay(); // 曜日

    var weeks = new Array('日','月','火','水','木','金','土');
    var number_type = day%2===0 ? '偶数' : '奇数'; // konokakikataSUKI
</script>

<div>
    <div>本日は{year}年{month}月{day}日{weeks[week]}曜日</div>
    <div>日付は{number_type}</div>
</div>