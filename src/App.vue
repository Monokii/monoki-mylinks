<template>
  <div>
    <h1>모노키</h1>
    <p>{{ dec }}</p>
  </div>
  <div style="display: flex; flex-wrap: wrap; justify-content: space-between; gap: 10px;">
    <div v-for="(item, i) in link" :key="i" class="linkbox">
      <div>
        <h3>{{ item.title }}</h3>
        <p>{{ item.description }}</p>        
      </div>
      <a :href="item.url" target="_blank">
        <button>바로가기</button>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data(){
    return {
      dec : '여기는 모노키의 링크들을 모아둔 곳이에요.',
      link : [
        {title: '우리.인생', description: '@so', url: "https://uri.life/@so"},
        {title: '스텔라.플레이스', description: '@so', url: 'https://stella.place/@so'},
        {title: '버터스콘', description: '@mono', url: 'https://buttersc.one/@mono'},
        {title: '깃허브', description: '@monokii', url: 'https://github.com/Monokii'},
        {title: '퀘스돈@플래닛', description: '@so@uri.life', url: 'https://quesdon.planet.moe/@so@uri.life'},
        {title: '네오-퀘스돈', description: '@so@uri.life', url: 'https://neo-quesdon.serafuku.moe/main/user/@so@uri.life'},
      ]
    }
  },
}
</script>

<style scoped>
  @import url("https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/variable/pretendardvariable.min.css");
  .linkbox {  
    display: flex;
    flex: 1;
    justify-content: space-between;
    align-items: center;
    min-width: 300px;
    border-radius: 10px;
    margin-top: 16px;
    padding: 18px;
    background-color: var(--color-background-soft);
  }
  button {
    padding: 10px 16px;
    border: none;
    border-radius: 30px;
    background-color: var(--color-background-r);
    color: var(--color-background);
    transition: 0.3s;
  }
  button:hover {
    padding: 10px 16px;
    border: none;
    border-radius: 10px;
    color: var(--color-background);
  }
</style>