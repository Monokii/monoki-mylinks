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
      <img src="https://i.imgur.com/nAHHSme.png" class="logo">
      <div style="display: flex;">
        <a v-for="(gnb, i) in memu" :key="i">{{ gnb.title }}</a>
      </div>
    </div>
    <div style="height: auto; justify-content: space-between; gap: 30px;">
      <div class="head">
        <h1>링크</h1>
        <p>{{ dec }}</p>
      </div>
      <div style="display: flex; flex-wrap: wrap; justify-content: space-between; gap: 20px; margin-top: 32px;">
        <div v-for="(item, i) in link" :key="i" class="linkbox">
          <div class="gap20">
            <div style="display: flex; gap: 8px;">
              <img :src="item.logo" :alt="item.title" />
              <img :src="item.avatar" :alt="item.profilealt" class="profileimg"/>
            </div>
            <div style="display: flex; flex-direction: column; gap: 5px;">
              <h3>{{ item.title }}</h3>
              <p>{{ item.description }}</p>
            </div>
          </div>
          <a :href="item.url" target="_blank">
            <button><a>바로가기</a></button>
          </a>
        </div>
      </div>
    </div>
    <div style="display: flex; justify-content: space-between;">
      <a>버전: {{ ver }}</a>
      <a>타입페이스: {{ font }}</a>
    </div>
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
        // 타이틀에는 사이트 제목을 입력하십시오. // 설명에는 짧게 아무말이나 기입하시오. // url에 프로필 링크를 기입하시오. // 사이트 로고 주소를 기입하시오. // 아바타 이미지 주소를 기입하시오. // 알트에 @닉네임 을 기입하시오.
        // 이미지 관리 // imgur로 불러오는 이미지를 관리하려면, 업로더의 계정을 사용하십시오.
        {title: '우리.인생', description: '올리고 싶을 때 올림.', url: "https://uri.life/@so", logo: "https://i.imgur.com/YTFDDCs.png", avatar: "https://nng-phinf.pstatic.net/MjAyNDExMjVfMTYw/MDAxNzMyNTQzNzI0NzEy.oBAql7C8HavBSCxN0vDUfV2twfN_XRGsHhDERsxJrzQg.EvZc3qTdpWwtsYgOT9C-OVPLh9rTAJ2wW0ZOUcvIqPgg.PNG/Bato-800x.png?type=f120_120_na", profilealt: '@so',}, //https://i.imgur.com/NDj2OVz.png, https://i.imgur.com/uc6LA96.png // 개인이 운영하는 소셜으로 보입니다 - 2024.1.2.부터 @so 아바타는 pstatic.net에서 불러옵니다.
        {title: '비발디 소셜', description: '한국인 얼마나 있을까 궁금.', url: "https://social.vivaldi.net/@Vivawa", logo: "https://i.imgur.com/KzPbRWO.png", avatar: "https://social-cdn.vivaldi.net/system/accounts/avatars/113/753/934/146/067/044/original/e52c4d59647eb912.png", profilealt: '@Vivawa',},
        {title: '스텔라', description: '별이래요.', url: 'https://stella.place/@so', logo: "https://for.stella.place/assets/Stella_R3_iOS_1024.png", avatar: "https://i.imgur.com/0ACyQ4l.png", profilealt: '@so',}, // 개인이 운영하는 소셜으로 보입니다 - 2024.1.2.부터 @so 아바타는 imgur에서 불러옵니다.
        {title: '버터스콘', description: '귀여운데, 규칙이 나랑 안 맞음.', url: 'https://buttersc.one/@mono', logo: "https://i.imgur.com/PODMlHB.png", profilealt: '@mono',}, // 개인이 운영하는 소셜으로 보입니다 - 2024.1.2.부터 @mono 아바타는 imgur에서 불러옵니다.
        {title: '표현의 모에들', description: '나쁘지 않지만, 쓸지 모르겠어요.', url: 'https://feels.moe/@monoki', logo: "https://files.feels.moe/feelsmoe/fa819c2a-a29d-46db-910f-ef0ebd75b225.png", avatar: "https://i.imgur.com/up6mqGt.png", profilealt: '',}, // 개인이 운영하는 소셜으로 보입니다 - 2024.1.2.부터 @monoki 아바타는 imgur에서 불러옵니다.
        {title: '칸트', description: '계정 만들어 놓고 까먹은 곳이에요.', url: 'https://iqhina.org/@o', logo: "https://iqhina.org/files/f8433f1c-48f1-4ef5-8aa6-40cc9f254820", avatar: "https://i.imgur.com/hiqvDqL.png", profilealt: '',}, // 개인이 운영하는 소셜으로 보입니다 - 2024.1.2.부터 @o 아바타는 imgur에서 불러옵니다.
        //{title: 'bsky', description: '잘 안 써요.', url: 'https://bsky.app/profile/yume.place', logo: "https://i.imgur.com/gN4l5CC.png"},
        {title: '깃허브', description: '딱히 뭐 없어요.', url: 'https://github.com/Monokii', logo: "https://i.imgur.com/NGvZ0c5.png", avatar: "https://avatars.githubusercontent.com/u/71020988?v=4", profilealt: '',},
        //{title: '치지직', description: '방송 안 해요.', url: 'https://chzzk.naver.com/8ce3e9df8179191c4e412a20065fbe1a', logo: "https://chzzk.org/wp-content/uploads/2023/12/chzzk-app.png"},
        {title: '숲프야', description: '안녕. 머독, 비챤 등...', url: 'https://ch.sooplive.co.kr/monoki', logo: "https://i.namu.wiki/i/8ASZvdHLwpdoP70VcLYL5Xkvw5B_udlhQ5ONgMTrr7h3nrOIn0otHti7aB9GvT4otdOcRe3s_GfCUu4a4BqpPGGHCD0fIrie7Z5F56Aqg7AO8FwvGHJZGubFp1b3zFJFMFXA_GoBeAxTHaTOEaJDzw.svg", avatar: "https://profile.img.sooplive.co.kr/LOGO/mo/monoki/monoki.jpg", profilealt: '',},
        {title: '내 튜브임.', description: '그냥 링크 걸려고 만들었어요.', url: 'https://www.youtube.com/@dowawonji', logo: "https://upload.wikimedia.org/wikipedia/commons/f/fd/YouTube_full-color_icon_%282024%29.svg", avatar: "https://yt3.googleusercontent.com/ytc/AIdro_l3Bz6doyOqmxnbxC7YTPEYDkB4EqydIAMsbEUjvC3cQlxG46o=s160-c-k-c0x00ffffff-no-rj", profilealt: '',},
        {title: 'ㄴㅋㄴㅋ(다시:돌아옴)', description: '방치 중...', url: 'https://www.nicovideo.jp/user/136988492/video', logo: "https://i.namu.wiki/i/eSuSYZDps8qnJws8bGQH8Ii-J5s9X5dt_F-BJle5EtFnH6AaTMoDspNaEJhExOEfXPvdi1uAJkN6VEEuKTYMRR7Hm1kBQPPAP2Uc72dveWFz-uuQyQcbyqTWi4lipb4Z6y6XUhEhvNdWxB0GB09_8g.svg", profileimg: "https://secure-dcdn.cdn.nimg.jp/nicoaccount/usericon/defaults/blank.jpg", profilealt: '',},
        {title: '사호슈', description: '특정 AI 아티스트 보려고 가입했어요. 241218', url: 'https://www.xiaohongshu.com/user/profile/6761b7480000000018014c9f', logo: "https://upload.wikimedia.org/wikipedia/commons/c/c1/XiaohongshuLOGO.svg", avatar: "https://sns-avatar-qc.xhscdn.com/avatar/1040g2jo31bvbukb5h00g5pr1mt462j4vq9d697o?imageView2/2/w/540/format/webp|imageMogr2/strip2", profilealt: '',},
        {title: 'X', description: '이상한 사람들 많은 곳.', url: 'https://x.com/DowawonJi', logo: "https://upload.wikimedia.org/wikipedia/commons/2/21/1690643591twitter-x-logo-png.webp", avatar: "", profilealt: '',},
        {title: '로블록스 프로필', description: '2017년 1월 부터 시작했어요, 넷카마 아니에요.', url: 'https://www.roblox.com/users/3638705580/profile', logo: "https://i.imgur.com/K5BwNkL.png", avatar: "https://tr.rbxcdn.com/30DAY-AvatarHeadshot-EAF040F46126B833E76BDA5D6DDA1450-Png/150/150/AvatarHeadshot/Webp/noFilter ", profilealt: '',},
        //{title: '안 씀1', description: '안 씀.', url: 'https://yume.place/'},
        //{title: '안 씀2', description: '도메인은 소셜 + 커넥트. TLD는 커뮤니티(co)임.', url: 'https://sonnect.co/'},
      ],
      memu : [
        //{title: '링크'},
      ],
      ver : '1.3.2025(+u2)',
      font : 'SUIT',
    }
  },
}
</script>

<style scoped>
  @import url("https://cdn.jsdelivr.net/gh/sun-typeface/SUIT@2/fonts/variable/woff2/SUIT-Variable.css");
  .logo {
    transform: scale(100%);
    transition: 0.6s ease;
  }
  .logo:hover {
    transform: scale(101%);
    background-color: #ffffff00;
  }
  .logo:active {
    transform: scale(200%);
    background-color: #E3F2FF;
    padding: 6px 7px;
    border-radius: 8px;
  }
  img {
    /* scale: 50%; */
    width: 52px;
    border-radius: 10px;
    transition: 0.5s ease;
    /* margin-bottom: 6px; */
  }
  /* img:active {
    transform: scale(323%);
    border-radius: 8px;
    background-color: #f9faff;
    padding: 5px;
  } */
  .profileimg {
    transform: scale(80%);
    border-radius: 100%;
    background: var(--color-border);
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
    padding: 12px 20px;
    display: flex;
    flex-direction: column;
    gap: 46px;
  }
  .gnb {
    /* background-color: var(--vt-c-monoki); */
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
    /* background-color: var(--color-background-hover); */
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
    h3 {
      transition: 0.3s;
    }
  }
  .linkbox:hover {
    border-radius: 52px 100px 52px 52px;
    margin-top: 3px;
    background-color: var(--color-background-hover);
    border: solid var(--color-background-r) 2px;
    transform: scale(1.03);
    img {
      transform: scale(1.1);
    }
    .profileimg {
      transform: scale(0.83);
    }
    h3 {
      null: null;
    }
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
  button a {
    font-weight: 700;
  }
  button a:hover {
    font-weight: 700;
  }
</style>