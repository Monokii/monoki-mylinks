<template>
  <div style="height: auto; justify-content: space-between; gap: 30px;">
    <div class="head">
      <h1>모노키</h1>
      <p>{{ dec }}</p>
    </div>
    <div style="display: flex; flex-wrap: wrap; justify-content: space-between; gap: 10px; margin-top: 10px;">
      <div v-for="(item, i) in link" :key="i" class="linkbox">
        <div>
          <h3>{{ item.title }}</h3>
          <p>{{ item.description }}</p>
        </div>
        <a :href="item.url" target="_blank">
          <button>이동</button>
        </a>
      </div>
    </div>
  </div>
  <div style="margin: 20px 0px;">
    <p>{{ ver }}</p>
    <p>와, 나 태어난 날이다.</p>
  </div>    
</template>

<script>
export default {
  name: 'App',
  data(){
    return {
      dec : '여기는 모노키의 링크들을 모아둔 곳이에요.',
      link : [
        {title: '우리.인생', description: '제가 주로 톳을 올리는 곳이죠.', url: "https://uri.life/@so"},
        {title: '스텔라.플레이스', description: '우리.인생이랑 둘 다 쓰다가 놔버린 곳이에요.', url: 'https://stella.place/@so'},
        {title: '버터스콘', description: '귀여워서 마음에는 들지만, 규칙이 저와는 안 맞아 보여요.', url: 'https://buttersc.one/@mono'},
        {title: '표현의 모에', description: '발언의 자유와 개인정보를 중점 운영이지만, 쓸지는 모름.', url: 'https://feels.moe/@monoki'},
        {title: '블루스카이', description: '트위터 탈중앙화 버전인데, 잘 안 써요.', url: 'https://bsky.app/profile/yume.place'},
        {title: '깃허브', description: '그냥 저의 깃허브 프로필 이에요, 딱히 뭐 없어요.', url: 'https://github.com/Monokii'},
        {title: '치지직', description: '흠?', url: 'https://chzzk.naver.com/8ce3e9df8179191c4e412a20065fbe1a'},
        {title: '로블록스 프로필', description: '2017년 1월 부터 시작했어요, 나쁘게 안 봐주셨으면 좋겠네요.', url: 'https://www.roblox.com/ko/users/3638705580/profile'},
        {title: '퀘스돈@플래닛', description: '질문 해보세요, 기다리고 있어요.', url: 'https://quesdon.planet.moe/@so@uri.life'},
        {title: '네오-퀘스돈', description: '질문 해보세요, 기다리고 있어요.', url: 'https://neo-quesdon.serafuku.moe/main/user/@so@uri.life'},
      ],
      ver : '12-09-2024v(meday)',
    }
  },
}
</script>

<style scoped>
  @import url("https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/variable/pretendardvariable.min.css");
  .head {
    display: flex;
    flex-direction: column;
    width: 80%;
  }
  .linkbox {  
    display: flex;
    flex: 1;
    justify-content: space-between;
    align-items: center;
    min-width: 300px;
    border-radius: 10px;
    margin-top: 5px;
    padding: 14px 18px;
    gap: 20px;
    background-color: var(--color-background-soft);
    border: solid var(--color-background-mute) 1px;
    transition: 0.3s;
  }
  .linkbox:hover {
    display: flex;
    flex: 1;
    justify-content: space-between;
    align-items: center;
    min-width: 300px;
    border-radius: 10px;
    margin-top: 5px;
    padding: 14px 18px;
    gap: 20px;
    background-color: var(--color-background-hover);
    border: solid var(--color-background-r) 2px;
    transition-delay: 1s;
    transform: scale(1.1);
  }
  button {
    white-space: nowrap;
    display: fixed;
    cursor: pointer;
    font-size: 16px;
    text-align: center;
    padding: 10px 16px;
    border: none;
    border-radius: 30px;
    background-color: var(--color-background-r);
    color: var(--color-background);
    transition: 0.28s;
  }
  button:hover {
    padding: 10px 16px;
    font-weight: 700;
    border: none;
    border-radius: 100px;
    color: var(--color-background);
    transform: scale(1.1);
  }
  button:active {
    padding: 10px 16px;
    font-weight: 700;
    border: none;
    border-radius: 100px;
    color: var(--color-background);
    opacity: 80%;
    transform: scale(0.94);
  }
</style>