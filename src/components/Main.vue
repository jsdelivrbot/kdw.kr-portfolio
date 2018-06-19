<template>
  <div id="main">
    <div :class="[$style['cover'], $style['box-lg']]">
      <div :class="$style['background']"></div>
      <div :class="$style['introduce']">
        <div :class="$style['name']">Kim-Daewoon</div>
        <div :class="$style['summary']">Student Developer</div>
        <div :class="$style['line']"></div>
        <div :class="$style['comment']">Korea Digital Media High School</div>
      </div>
    </div>
    <div :class="[$style['projects'], $style['box-sm']]">
      <div :class="$style['title']">프로젝트 소개</div>
    </div>
    <div :class="[$style['project'], $style['box-sm']]" v-for="item in projects">
      <div :class="$style['background']" :style="{ 'background-image': 'url(' + item.image + ')' }"></div>
      <div :class="$style['title']">
        {{item.name}}
      </div>
      <div :class="$style['content']" v-html="item.desc"></div>
    </div>
    <div :class="[$style['activities'], $style['box-sm']]">
      <div :class="$style['title']">활동 경력</div>
    </div>
    <div :class="[$style['project'], $style['box-sm']]" v-for="item in activities">
      <div :class="$style['background']" :style="{ 'background-image': 'url(' + item.image + ')' }"></div>
      <div :class="$style['title']">
        {{item.name}}
      </div>
      <div :class="$style['content']" v-html="item.desc"></div>
    </div>
    <div :class="[$style['awards'], $style['box']]">
      <div :class="$style['title']">수상 경력</div>
      <div :class="$style['content']">
        <div v-for="item in awards">
          <div :class="$style['name']">{{item.name}}</div>
          <div :class="$style['result']">{{item.result}}</div>
        </div>
      </div>
    </div>
    <div :class="[$style['career'], $style['box']]">
      <div :class="$style['title']">기술 경력</div>
      <div :class="$style['content']">
        <div :class="$style['item']" v-for="item in career">
          <div :class="$style['name']">{{item.name}}</div>
          <div :class="$style['start']">{{item.start}}~</div>
          <div :class="$style['level']">{{item.level}}</div>
        </div>
      </div>
    </div>
    <div :class="[$style['introduce'], $style['box']]">
      <div :class="$style['title']">소개</div>
      <div :class="$style['content']">
        <img src="../assets/me.jpg" height=200>
        <p>안녕하세요. 한국디지털미디어고등학교에 재학중인 김대운 입니다.<br>초등학교 4학년부터 프로그래밍에 관심을 갖게 되었고, 초등학교 5학년부터 본격적으로 시작하게 되었습니다. 현재 웹/서버 개발을 중심으로 하고 있습니다.</p>
      </div>
    </div>
    <div :class="[$style['contact'], $style['box']]">
      <div :class="$style['title']">연락처</div>
      <div :class="$style['content']">
        <div v-for="contact in contacts">
          <icon :name="contact.icon" scale="2"/>
          <a :href="contact.url"> {{contact.name}}</a>
        </div>
      </div>
    </div>
    <div :class="[$style['footer'], $style['box-sm']]">
      <div :class="$style['content']">
        ⓒ 2018 kdwkr (Kim-Daewoon)&lt;me@kdw.kr&gt;
      </div>
    </div>
  </div>
</template>

<script>
import KKuTuKorea from '@/assets/kkuko.png'
import DimigoLife from '@/assets/dimigolife.png'
import Luna from '@/assets/luna.jpg'
import Kuze from '@/assets/kuze.png'
export default {
  data () {
    return {
      awards: [
        {name: '충청남도교육연구정보원 스마트리더영재교육원', result: '중등심화 수료'},
        {name: 'AppJam 미래산업부분(IoT)', result: '최우수상'},
        {name: '산업 현장 안전 메이커톤', result: '대상'},
        {name: '한국청소년정보과학회 해커톤', result: '특별상'},
      ],
      projects: [
        {name: '끄투코리아', desc: '끄투코리아는 끝말잇기를 웹게임으로 재구성한 온라인 게임이며, 2017년 2월 16일에 서비스를 시작하였습니다. 원작인 "끄투" 오픈소스를 입맛에 맞게 개조하여 운영중입니다.<br><br>끄투코리아팀에서 총괄 및 개발을 맡고 있습니다.', image: KKuTuKorea},
        {name: '디미고라이프', desc: '디미고라이프는 한국디지털미디어고등학교 기숙사 인트라넷으로 2018년 3월부터 시작하였습니다. 잔류, 간식, 금요귀가 신청 등 디미고 생활과 관련한 기능을 제공하고 있습니다.<br><br>디미고라이프팀에서 프론트엔드 개발을 주로 맡고 있습니다.', image: DimigoLife}
      ],
      activities: [
        {name: '루나 LUNA', desc: '교내 창업 동아리로, \'세상을 비추는 달, 코딩\'이라는 모토를 가진 창업 동아리이자 꿈을 사는 동아리 입니다. 올해에는 \'코딩 교육 플랫폼\'이라는 창업 아이템을 중심으로 여러 창업 아이템을 개발합니다.<br><br>루나에서 개발을 맡고 있습니다.', image: Luna},
        {name: 'KUZE In Dimigo', desc: '교내 창업 동아리로, 한국디지털미디어고등학교 유일의 청소년 기업동아리로써 4차 산업혁명 시대에 걸맞는 청소년 기업가를 양성하는 동아리 입니다. 본 동아리는 엔터테인먼트(MCN), 소프트웨어, 교육, 공익사업 드의 사업을 폭넓게 펼쳐 동아리원 모두가 각자 자신의 능력과 꿈을 이루기 위하여 지원하고 있습니다.<br><br>쿠즈에서 개발을 맡고 있습니다.', image: Kuze}
      ],
      career: [
        {name: 'Javascript', start: '2014', level: '중급'},
        {name: 'Android(Java)', start: '2014', level: '중급'},
        {name: 'HTML', start: '2015', level: '고급'},
        {name: 'CSS', start: '2015', level: '중급'},
        {name: 'Jquery', start: '2015', level: '중급'},
        {name: 'C', start: '2015', level: '입문'},
        {name: 'C#', start: '2015', level: '중급'},
        {name: 'VB.net', start: '2015', level: '중급'},
        {name: 'Arduino', start: '2015', level: '초급'},
        {name: 'PHP', start: '2015', level: '초급'},
        {name: 'Java', start: '2016', level: '초급'},
        {name: 'Node.js', start: '2016', level: '고급'},
        {name: 'Python', start: '2016', level: '입문'},
        {name: 'Android(Kotlin)', start: '2017', level: '초급'},
        {name: 'Pug', start: '2017', level: '중급'},
        {name: 'Electron', start: '2018', level: '초급'},
        {name: 'Vue.js', start: '2018', level: '중급'},
      ],
      contacts: [
        {name: 'Github', icon: 'brands/github', url: 'https://github.com/kdwkr'},
        {name: 'Facebook', icon: 'brands/facebook', url: 'http://fb.com/kdwkr0410'},
        {name: 'Instagram', icon: 'brands/instagram', url: 'https://www.instagram.com/kdwkr'},
        {name: 'Messenger', icon: 'brands/facebook-messenger', url: 'https://m.me/kdwkr0410'},
        {name: 'me@kdw.kr', icon: 'envelope', url: 'mailto:me@kdw.kr'}
      ]
    }
  }
}
</script>

<style lang="scss" module>
.line {
  width: 10rem;
  height: 0.05rem;
  background-color: #ccc;
  margin: 0.5rem auto;
}
.cover {
  background-color: #000;
  color: #f7fff7;

  .background {
    z-index: 1;
    position: absolute;
    width: 100%;
    height: 100%;
    background: url(../assets/bg.jpg) no-repeat center center fixed;
    background-size: cover;
    opacity: 0.4;
    left: 0;
  }

  .introduce {
    z-index: 2;
    color: #fff;
    text-align: center;

    &::before {
      display: table;
      content: " ";
    }
    &::after {
      clear: both;
      display: table;
      content: " ";
    }
    .name {
      font-weight: 800;
      font-size: 3rem;
    }
    .summary {
      font-weight: 300;
      font-size: 2rem;
    }
    .comment {
      font-weight: 300;
    }
  }
}
.projects {
  background-color: #92afd7;
}
.activities {
  background-color: #D3F8E2;
}
.project {
  background-color: #000;
  .title, .content {
    z-index: 2;
    color: #f1e3f3;
  }
  .background {
    z-index: 1;
    position: absolute;
    width: 100%;
    height: 100%;
    background: url() no-repeat center center fixed;
    background-size: cover;
    opacity: 0.4;
    left: 0;
  }
}
.awards {
  background-color: #f7fff7;
  color: #25283d;
  .name {
    margin-top: 1rem;
    font-size: 0.8em;
  }
  .result {
    font-weight: 500;
  }
}
.career {
  background-color: #e8f1f2;
  .content{
    display: flex;
    flex-direction: column;
    flex-flow: row wrap;
    justify-content: space-evenly;
  }
  .item {
    box-shadow: #ccc 5px 5px 10px;
    width: 15rem;
    border-radius: 5px;
    background-color: #fff;
    margin: 0.5rem 0.2rem 1rem 0.2rem;
    padding: 0.5rem;
    position: relative;

    .name {
      font-weight: 700;
      font-size: 0.8em;
    }
    .start {
      font-weight: 400;
      font-size: 0.6em;
    }
    .level {
      font-weight: 300;
      font-size: 1rem;
      position: absolute;
      right: 0.5rem;
      bottom: 0.5rem;
    }
  }
}
.contact {
  background-color: #a0a4b8;
  .content {
    text-align: center;
    div {
      display: block;
      width: 13rem;
      flex: 1;
      margin-left: auto;
      margin-right: auto;
      margin-bottom: 0.25rem;
      text-align: left;
    }
    svg {
      margin-right: 0.25rem;
    }
    a {
      display: inline-block;
      color: #000;
      text-decoration: none;
    }
  }
}
.footer {
  background-color: #eadeea;
}
.box, .box-sm, .box-lg {
  min-height: 50vh;
  width: calc(100% - 10rem);
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: center;
  text-align: center;
  padding: 5rem 5rem;
  &-lg {
    min-height: 80vh;
  }
  &-sm {
    min-height: 20vh;
  }
  .title {
    font-weight: 800;
    font-size: 2.5rem;
  }
  .content {
    margin-top: 2rem;
    font-weight: 300;
    font-size: 1.8rem;
    word-break: keep-all;
    word-wrap: break-word;
  }
}
</style>
