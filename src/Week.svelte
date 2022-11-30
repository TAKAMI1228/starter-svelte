<script lang="ts">
    import Day from "./Day.svelte";
  
    export let startDate: Date;
  
    // 1週間のDateオブジェクトの配列
    //i=0は赤（日曜日）　i=6は青（土曜日）
    const week = Array.from(Array(7).keys(), (i) => {
      const date = new Date(startDate);
      //const str_date = new Date(startDate);
      //str_date.setDate(startDate.getDate() + i);
      //const date: {[key: number]:Date} = {};
      date.setDate(startDate.getDate() + i);
      //date[i] = str_date;
      //return date;
      return date;
    });
  </script>
  
  <style>
    div {
      display: flex;
      flex: 1;
    }
  </style>
  
  <div class="week">
    {#each week as date}
      <Day {date}/>
    {/each}
  </div>