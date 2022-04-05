<template>
  <main class="main">
    <div class="main__wrapper">
      <MainImage :num="activeSlide" />
      <ProgressBar v-if="activeSlide != 0 || activeSlide != 4" :progress="qNum" />
      <div :class="{ 'exp-active': isExp }" class="exp">
        <img src="@/assets/img/plus.png" alt="" />
      </div>
      <MainButton
        v-if="activeSlide == 0"
        @click="activeSlide++"
        :text="btns[activeSlide]"
      />
      <MainButton
        v-else-if="qNum < 24"
        @click="
          showModal = true;
          isExp = false;
        "
        :text="btns[activeSlide]"
      />
      <MainButton v-else @click="fin = true" :text="btns[activeSlide]" />
    </div>
    <MainModal
      v-if="qNum < 24"
      :question="questions[qNum]"
      v-show="this.showModal"
      @close="modalClosed"
    />
    <MainFin v-show="fin" :prof="calculateProf()" @goTest="fin = false" />
  </main>
</template>

<script>
import MainImage from "@/components/MainImage";
import MainButton from "@/components/MainButton";
import MainModal from "@/components/MainModal";
import ProgressBar from "@/components/ProgressBar";
import MainFin from "@/components/MainFin";
export default {
  name: "App",
  data() {
    return {
      activeSlide: 0,
      qNum: 0,
      isExp: false,
      btns: ["Войти в IT", "Давай!", "Ещё вопрос!", "Погнали!", "Да, капитан!"],
      showModal: false,
      fin: false,
      questions: [
        {
          prof: "frontend",
          text: "Вы спокойно можете освоить что-то новое и любите оперировать передовыми методами в той или иной сфере.",
        },
        {
          prof: "frontend",
          text: "Вы не против того, чтобы быть в центре внимания.",
        },
        {
          prof: "frontend",
          text: "Вы любите подключать абстрактное мышление и смотреть на решение вопроса с другой стороны.",
        },
        { prof: "frontend", text: "Вам нравится ни от кого не зависеть." },

        { prof: "backend", text: "Вы любите БОЛЬШИЕ и БЫСТРЫЕ компьютеры." },
        {
          prof: "backend",
          text: "Вы часто погружаетесь в свои мысли, что не замечаете или забываете об окружающих вас людях?",
        },
        {
          prof: "backend",
          text: "Вам нравится ходить на мероприятия, которые связаны с ролевыми играми.",
        },
        {
          prof: "backend",
          text: "При любых условиях вы пытаетесь делать все максимально идеально и понятно.",
        },

        {
          prof: "ds",
          text: "Вы любите математику и не прочь повисеть над какой-то нелёгкой задачкой.",
        },
        { prof: "ds", text: "Вам нравится структурировать данные." },
        {
          prof: "ds",
          text: "Вы считаете себя больше практичным, чем креативным человеком.",
        },
        {
          prof: "ds",
          text: "Когда речь идет о принятии важных решений для вас логика, как правило, важнее чувств.",
        },

        {
          prof: "gamedev",
          text: "Ваш стиль работы можно скорее охарактеризовать как беспорядочные всплески энергии, а не методичная и организованная деятельность.",
        },
        {
          prof: "gamedev",
          text: "Вам не чуждо прислушиваться к чьим-то требований, жертвуя творчеством, удовлетворяя желания клиента.",
        },
        {
          prof: "gamedev",
          text: "Прочитав книгу или посмотрев фильм - вы любите их анализировать.",
        },
        { prof: "gamedev", text: "Мир игр вам не чужд." },

        {
          prof: "designer",
          text: "В жизни вы любите ко всему подходить с креативом.",
        },
        {
          prof: "designer",
          text: "У вас хорошо развита способность визуализировать информацию , передавать идею в изображение?",
        },
        {
          prof: "designer",
          text: "Вы умеете и любите использовать Photoshop.",
        },
        { prof: "designer", text: "Рисование вам не чуждо." },

        { prof: "qa", text: "Внимательный ли вы человек?" },
        { prof: "qa", text: "Вас напрягают барьеры?" },
        { prof: "qa", text: "Вы относительно сдержанный и спокойный человек." },
        {
          prof: "qa",
          text: "На сколько вас раздражает, когда вы не можете быстро найти нужную информацию на сайте?",
        },
      ].sort(() => Math.random() - 0.5),
      profs: {
        frontend: 0,
        backend: 0,
        designer: 0,
        qa: 0,
        gamedev: 0,
        ds: 0,
      },
    };
  },
  components: {
    MainImage,
    MainButton,
    MainModal,
    ProgressBar,
    MainFin,
  },
  methods: {
    modalClosed(arr) {
      this.showModal = false;
      this.isExp = true;
      this.profs[arr[1]] = this.profs[arr[1]] + Number(arr[0]);
      this.qNum++;
      if (this.qNum % 8 == 0) this.activeSlide++;
    },
    calculateProf() {
      const arr = Object.entries(this.profs);
      let max = -1;
      let prof = "";
	  const t = []
      arr.forEach((element) => {
        if (element[1] >= max) {
          prof = element[0];
          max = element[1];
		  t.push(prof);
        }
      });
      return t[Math.floor(Math.random() * t.length)];
    },
    computed: {},
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Open+Sans&display=swap");

* {
  margin: 0;
  padding: 0;
}

body {
  background: linear-gradient(250deg, #4eb848 0%, #4e8a4b 100%);
  font-family: "Open Sans";
}

.main {
  width: 90vw;
  height: 80vh;
  overflow: hidden;
  margin: 0 auto;
  &__wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
}

.exp {
  position: absolute;
  left: 0;
  top: 50%;
  border-radius: 8px;
  transform: translate(-100%, 50%);
  transition: transform 0.5s ease;
  &-active {
    transform: translate(0, 50%);
    & img {
      box-shadow: 0px 4px 16px 4px #fff32a;
      border-radius: 8px;
    }
  }
}

@media (max-width: 570px) {
  .main {
    width: 100vw;
  }
}
</style>
