<template>
  <div style="display: flex;">
    <!--
    <div class="sidebar">
    사이드바 내용
      <h2 style="margin: 5px 14px;">모노키</h2>
      <a>홈</a>
      <a>dkanrjask</a>
    </div>  -->

    <div class="page">
      <div class="gnb">
      <h3>모노키</h3>
      <div style="display: flex;">
        <a v-for="(gnb, i) in memu" :key="i">{{ gnb.title }}</a>
      </div>
    </div>
    <div style="padding: 0px 8px; height: auto; justify-content: space-between; gap: 30px;">
      <div class="head">
        <h1>링크</h1>
        <p>{{ dec }}</p>
      </div>
      <div style="display: flex; flex-wrap: wrap; justify-content: space-between; gap: 10px; margin-top: 10px;">
        <div v-for="(item, i) in link" :key="i" class="linkbox">
          <div class="gap20">
            <div>
              <h3>{{ item.title }}</h3>
              <p>{{ item.description }}</p>
            </div>
            <img :src="item.logo">
          </div>
          <a :href="item.url" target="_blank">
            <button>이동</button>
          </a>
        </div>
      </div>
    </div>
    <a>v: {{ ver }}</a>
  </div>
  </div>

</template>

<script>
export default {
  name: 'App',
  data(){
    return {
      dec : '여기는 모노키의 링크들을 모아둔 곳이에요.<br/>사이트 이름들은 제 마음대로 부를 거예요.',
      link : [
        {title: '우리.인생', description: '제가 주로 톳을 올리는 곳이죠.', url: "https://uri.life/@so", logo: "/src/assets/services-icon/uri-life-logo-vector.svg"},
        {title: '스텔라.플레이스', description: '음.', url: 'https://stella.place/@so', logo: "https://for.stella.place/assets/Stella_R3_iOS_1024.png"},
        {title: '버터스콘', description: '귀엽지만, 규칙이 저와는 안 맞아요.', url: 'https://buttersc.one/@mono', logo: "https://box.buttersc.one/bucket/c998ed88-0531-4299-b304-c95f60fb1b16.webp"},
        {title: '표현의 모에', description: '나쁘지 않지만, 쓸지 모르겠어요.', url: 'https://feels.moe/@monoki', logo: "https://files.feels.moe/feelsmoe/5d38655a-b6a0-4d3a-9be5-dda3e7acee9f.png"},
        {title: '칸노트', description: '계정 만들어 놓고 까먹은 곳이에요.', url: 'https://iqhina.org/@o', logo: "https://iqhina.org/files/f8433f1c-48f1-4ef5-8aa6-40cc9f254820"},
        {title: '블루스카이', description: '잘 안 써요.', url: 'https://bsky.app/profile/yume.place', logo: "/src/assets/services-icon/bsky-logo-vector.svg"},
        {title: '깃허브', description: '딱히 뭐 없어요.', url: 'https://github.com/Monokii', logo: "/src/assets/services-icon/github-logo-vector.svg"},
        {title: '치지직', description: '흠?', url: 'https://chzzk.naver.com/8ce3e9df8179191c4e412a20065fbe1a', logo: "https://chzzk.org/wp-content/uploads/2023/12/chzzk-app.png"},
        {title: '유튜브', description: '그냥 링크 걸려고 만들었어요.', url: 'https://www.youtube.com/@yume_place'},
        {title: '도코도코(다시:돌아옴)', description: '아 nicopatty가 생각나요.', url: 'https://www.nicovideo.jp/user/136988492/video'},
        {title: '샤오훙수', description: '특정 그림 아티스트 보려고 가입했어요. 241218', url: 'https://www.xiaohongshu.com/user/profile/6761b7480000000018014c9f'},
        {title: 'X', description: '뭐라고 써야할까', url: 'https://x.com/DowawonJi'},
        {title: '로블록스 프로필', description: '2017년 1월 부터 시작했어요, 넷카마 아니에요.', url: 'https://www.roblox.com/users/3638705580/profile'},
        {title: '퀘스돈@플래닛', description: '질문 하던말던.', url: 'https://quesdon.planet.moe/@so@uri.life'},
        {title: '네오-퀘스돈', description: '질문 하던말던.', url: 'https://neo-quesdon.serafuku.moe/main/user/@so@uri.life'},
        {title: '실험용1', description: '내가 하고싶은 걸 시도해보고, 여러가지를 하는 곳.', url: 'https://yume.place/'},
        {title: '실험용2', description: '도메인은 소셜 + 커넥트. TLD는 커뮤니티(co)임.', url: 'https://sonnect.co/'},
      ],
      memu : [
        {title: '링크'},
      ],
      ver : '12-18-2024',
    }
  },
}
</script>

<style scoped>
  @import url("https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/variable/pretendardvariable.min.css");
  img {
    width: 32px;
    margin-bottom: 6px;
  }
  .sidebar {
  width: 250px; /* 사이드바 너비 */
  height: 100vh; /* 화면 전체 높이 */
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  background-color: var(--color-background-soft);
  position: fixed; /* 화면 왼쪽에 고정 */
  top: 0px;
  left: 0px;
  padding: 16px 10px;
  box-shadow: 2px 0 5px rgba(0, 0, 0, 0.1);
  }
  .sidebar a {
    padding: 10px 14px;
    transition: 0.2s;
    cursor: pointer;
    border-radius: 5px;
  }
  .sidebar a:hover {
    padding: 10px 14px;
    color: var(--color-background-rh);
    background-color: var(--color-background-hover);
  }
  .page {
    /* margin-left: 250px; */
    padding: 0px 20px;
    display: flex;
    flex-direction: column;
    gap: 24px;
  }
  .gnb {
    display: flex;
    background-color: var(--color-background-soft);
    padding: 2px 20px;
    border-radius: 10px;
    align-items: center;
    /* align-self: center;
    align-self: start; */
    gap: 14px;
  }
  .gnb a {
    border-radius: 0px;
    padding: 16px 16px;
    border-radius: 40px;
    transition: 0.32s;
    cursor: pointer;
  }
  .gnb a:hover {
    padding: 16px 20px;
    border-radius: 5px;
    color: var(--color-background-rh);
    background-color: var(--color-background-hover);
  }
  .gnb a:active {
    padding: 16px 20px;
    color: var(--color-background-rh);
    border-radius: 10px;
    opacity: 0.8;
    transform: scale(0.9);
    /* border-bottom: 2px solid var(--color-background-rh); */
  }
  .head {
    display: flex;
    flex-direction: column;
    width: 80%;
  }
  .gap20 {
    display: flex;
    flex-direction: column;
    gap: 8px;
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