<template>
  <div style="display: flex;">
    <!--
    <div class="sidebar">
    사이드바 내용 2024 - 12 - 03
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
      <div style="display: flex; flex-wrap: wrap; justify-content: space-between; gap: 20px; margin-top: 32px;">
        <div v-for="(item, i) in link" :key="i" class="linkbox">
          <div class="gap20">
            <img :src="item.logo">
            <div style="display: flex; flex-direction: column; gap: 5px;">
              <h3>{{ item.title }}</h3>
              <p>{{ item.description }}</p>
            </div>
          </div>
          <a :href="item.url" target="_blank">
            <button>바로가기</button>
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
      dec : '여기는 링크를 모아둔 곳이에요. 사이트 이름들은 제 마음대로 부를 거예요.',
      link : [
        {title: '우리.인생', description: '올리고 싶을 때 올림.', url: "https://uri.life/@so", logo: "https://i.imgur.com/NDj2OVz.png"},
        {title: '스텔라', description: '별이래요.', url: 'https://stella.place/@so', logo: "https://for.stella.place/assets/Stella_R3_iOS_1024.png"},
        {title: '버터스콘', description: '귀여운데, 규칙이 나랑 안 맞음.', url: 'https://buttersc.one/@mono', logo: "https://box.buttersc.one/bucket/c998ed88-0531-4299-b304-c95f60fb1b16.webp"},
        {title: '표현의 모에들', description: '나쁘지 않지만, 쓸지 모르겠어요.', url: 'https://feels.moe/@monoki', logo: "https://files.feels.moe/feelsmoe/fa819c2a-a29d-46db-910f-ef0ebd75b225.png"},
        {title: '칸트', description: '계정 만들어 놓고 까먹은 곳이에요.', url: 'https://iqhina.org/@o', logo: "https://iqhina.org/files/f8433f1c-48f1-4ef5-8aa6-40cc9f254820"},
        {title: '파하늘', description: '잘 안 써요.', url: 'https://bsky.app/profile/yume.place', logo: "https://i.imgur.com/gN4l5CC.png"},
        {title: '깃허브', description: '딱히 뭐 없어요.', url: 'https://github.com/Monokii', logo: "/src/assets/services-icon/github-logo-vector.svg"},
        {title: '치지ㅊ직ㅈㅈㅊ', description: '흠?', url: 'https://chzzk.naver.com/8ce3e9df8179191c4e412a20065fbe1a', logo: "https://chzzk.org/wp-content/uploads/2023/12/chzzk-app.png"},
        {title: '숲프야', description: '안녕. 머독, 비챤 등...', url: 'https://ch.sooplive.co.kr/monoki', logo: "https://i.namu.wiki/i/TdjyiuKhQk8SnlEHVt0hekEIfHCnDGKlR1qGvSBQohuhFlcPYio3dMb60KYZdDxQJiDzfdnb4hESiXz_GqIf7w.svg"},
        {title: '내 튜브임.', description: '그냥 링크 걸려고 만들었어요.', url: 'https://www.youtube.com/@yume_place', logo: "https://upload.wikimedia.org/wikipedia/commons/f/fd/YouTube_full-color_icon_%282024%29.svg"},
        {title: 'ㄷㅋㄷㅋ(다시:돌아옴)', description: '방치 중...', url: 'https://www.nicovideo.jp/user/136988492/video', logo: "https://i.namu.wiki/i/GHIaThfebPpxVe8rbu2zx8YqQXe5cnNmmfY32waFRTBROYkjSiwJi3QC87tNxH5rO8Qtvc4tobshoHbv0oP_BCCG_Q7xGxh8fhvuwK_pzJgIhf2Dkjs-gyXstocj9m3IaZ0O6nnBSXnhT2_t7Utzvg.svg"},
        {title: '사호슈', description: '특정 AI 아티스트 보려고 가입했어요. 241218', url: 'https://www.xiaohongshu.com/user/profile/6761b7480000000018014c9f', logo: "https://upload.wikimedia.org/wikipedia/commons/c/c1/XiaohongshuLOGO.svg"},
        {title: 'X', description: '이상한 사람들 많은 곳.', url: 'https://x.com/DowawonJi', logo: "https://upload.wikimedia.org/wikipedia/commons/2/21/1690643591twitter-x-logo-png.webp"},
        {title: '로잼록스 프로필', description: '2017년 1월 부터 시작했어요, 넷카마 아니에요.', url: 'https://www.roblox.com/users/3638705580/profile', logo: "https://static.wikia.nocookie.net/robloxcities/images/d/d2/RobloxLogo.png/revision/latest/scale-to-width-down/1000?cb=20230125021936"},
        {title: '안 씀1', description: '안 씀.', url: 'https://yume.place/'},
        {title: '안 씀2', description: '도메인은 소셜 + 커넥트. TLD는 커뮤니티(co)임.', url: 'https://sonnect.co/'},
      ],
      memu : [
        //{title: '링크'},
      ],
      ver : '12-27-2024-ui-3',
    }
  },
}
</script>

<style scoped>
  @import url("https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/variable/pretendardvariable.min.css");
  img {
    /* scale: 50%; */
    width: 52px;
    border-radius: 10px;
    transition: 0.4s ease;
    /* margin-bottom: 6px; */
  }
  img:active {
    transform: scale(320%);
    border-radius: 3px;
    background-color: #fff;
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
    gap: 46px;
  }
  .gnb {
    background-color: var(--vt-c-monoki);
    padding: 6px 14px;
    border-radius: 12px;
    align-self: center;
    align-items: center;
    /* align-self: center;
    align-self: start; */
    gap: 14px;
    transition: 0.3s;
    cursor: default;
  }
  .gnb:hover {
    background-color: var(--color-background-hover);
    transform: scale(1.1);
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
    align-items: center;
    gap: 8px;
    flex-direction: column;
  }
  .gap20 {
    display: flex;
    flex-direction: column;
    align-items: left;
    gap: 26px;
  }
  .linkbox {
    display: flex;
    flex-direction: column;
    flex: 1;
    justify-content: space-between;
    align-items: left;
    min-width: 300px;
    max-width: 379px;
    border-radius: 94px 42px 94px 94px;
    margin-top: 3px;
    padding: 60px 34px 72px;
    gap: 20px;
    background-color: var(--color-background-soft);
    border: solid var(--color-background-soft) 1px;
    transition: 0.34s;
  }
  .linkbox:hover {
    border-radius: 52px 100px 52px 52px;
    margin-top: 3px;
    background-color: var(--color-background-hover);
    border: solid var(--color-background-r) 2px;
    transform: scale(1.05);
  }
  button {
    white-space: nowrap;
    display: fixed;
    cursor: pointer;
    font-size: 16px;
    text-align: center;
    padding: 14px 22px;
    border: none;
    border-radius: 30px;
    background-color: var(--color-background-r);
    color: var(--color-background);
    transition: 0.28s;
    font-weight: 600;
  }
  button:hover {
    font-weight: 700;
    border: none;
    border-radius: 100px;
    color: var(--color-background);
    transform: scale(1.1);
  }
  button:active {
    font-weight: 800;
    border: none;
    border-radius: 100px;
    color: var(--color-background);
    opacity: 80%;
    transform: scale(0.94);
  }
</style>