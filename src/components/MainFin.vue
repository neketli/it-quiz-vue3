<template>
  <transition name="fade">
    <div class="modal-mask">
      <div class="modal-wrapper">
        <div v-if="prof === 'frontend'" class="modal-container">
          <div class="modal-header">
            <slot name="header">
              <h3>Вам больше всего подходит профессия:</h3>
              <h2>Frontend разработчик</h2>
            </slot>
          </div>

          <div class="modal-body">
            <slot name="body">
              <div class="body-wrapper">
                <div class="description">
                  <h4>Чем занимаются фронтендеры?</h4>
                  <p>
                    Эта профессия — как может показаться, один из самых простых
                    "входов в IT", хотя если копнуть немного глубже базовых
                    знаний верстки, оказывается, что она едва ли не сложнее всех
                    остальных. По сути, фронтенд — это всё то, что видит
                    пользователь при открытии web-страницы. Во фронтенде вас
                    ожидают интересные задачи требующие элегантных решений в
                    сфере разработки интерфейсов веб приложений :)
                  </p>
                  <span
                    >Хочешь развиваться в этой теме? Оставляй заявку на сайте и
                    мы с тобой свяжемся!</span
                  >
                </div>
                <div class="image">
                  <img src="@/assets/img/profs/front.png" alt="" />
                </div>
              </div>
            </slot>
          </div>

          <div class="modal-footer">
            <slot name="footer">
              <form action="https://talents.centrinvest.ru/">
                <MainButton class="modal-button" text="Хочу дальше!" />
              </form>
            </slot>
          </div>
        </div>
        <div v-else-if="prof === 'backend'" class="modal-container">
          <div class="modal-header">
            <slot name="header">
              <h3>Вам больше всего подходит профессия:</h3>
              <h2>Backend разработчик</h2>
            </slot>
          </div>

          <div class="modal-body">
            <slot name="body">
              <div class="body-wrapper">
                <div class="description">
                  <h4>Чем занимаются бэкендеры?</h4>
                  <p>
                    Бэкенд-разработчик отвечает за то, чего пользователю не
                    видно — всё, что спрятано «под капотом», то есть работает на
                    сервере. Например, когда заказывая Uber, вы вводите адрес,
                    выбираете тип машины и оплачиваете поездку, то за «магию»,
                    которая срабатывает на другой стороне, отвечает backend.
                    Если вы хотите, чтобы все приложения мира работали быстрее
                    скорости света, красиво и качественно хранили информацию,то
                    вам сюда :)
                  </p>
                  <span
                    >Хочешь развиваться в этой теме? Оставляй заявку на сайте и
                    мы с тобой свяжемся!</span
                  >
                </div>
                <div class="image">
                  <img src="@/assets/img/profs/back.png" alt="" />
                </div>
              </div>
            </slot>
          </div>

          <div class="modal-footer">
            <slot name="footer">
              <form action="https://talents.centrinvest.ru/">
                <MainButton class="modal-button" text="Хочу дальше!" />
              </form>
            </slot>
          </div>
        </div>
        <div v-else-if="prof === 'qa'" class="modal-container">
          <div class="modal-header">
            <slot name="header">
              <h3>Вам больше всего подходит профессия:</h3>
              <h2>QA инженер</h2>
            </slot>
          </div>

          <div class="modal-body">
            <slot name="body">
              <div class="body-wrapper">
                <div class="description">
                  <h4>Чем занимаются тестировщики?</h4>
                  <p>
                    Тестировщики, или QA-инженеры, — это люди, которые
                    проверяют, как работает программа или приложение. Они ищут
                    ошибки, смотрят, чтобы программа делала именно то, что
                    задумано, защищают продукт от хакеров, проверяют, как
                    приложение работает на разных устройствах и в разных
                    операционных системах. На самом деле тестировщик — это
                    сложная и творческая профессия. Так что. если ты любишь
                    ломать, крушить и творить, то беги скорее сюда! :)
                  </p>
                  <span
                    >Хочешь развиваться в этой теме? Оставляй заявку на сайте и
                    мы с тобой свяжемся!</span
                  >
                </div>
                <div class="image">
                  <img src="@/assets/img/profs/qa.png" alt="" />
                </div>
              </div>
            </slot>
          </div>

          <div class="modal-footer">
            <slot name="footer">
              <form action="https://talents.centrinvest.ru/">
                <MainButton class="modal-button" text="Хочу дальше!" />
              </form>
            </slot>
          </div>
        </div>
        <div v-else-if="prof === 'designer'" class="modal-container">
          <div class="modal-header">
            <slot name="header">
              <h3>Вам больше всего подходит профессия:</h3>
              <h2>UI/UX designer</h2>
            </slot>
          </div>

          <div class="modal-body">
            <slot name="body">
              <div class="body-wrapper">
                <div class="description">
                  <h4>Чем занимаются дизайнеры интерфейсов?</h4>
                  <p>
                    Дизайнер - это своеобразный игрок в покер, только знай, что
                    блефовать не получится :) В своих решения дизайнер
                    основывается на исследовании привычек, культурных
                    предпочтений и стремлений людей. Также дизайнер сопровождает
                    продукт пока тот врастает в рынок и помогает собирать
                    обратную связь о повышении качества жизни и делать выводы о
                    следующих шагах в развитии. Ну что, я тебя заинтересовал?
                    Так давай сыграем партию и возможно ты станешь самой опасной
                    акулой в этой сфере :)
                  </p>
                  <span
                    >Хочешь развиваться в этой теме? Оставляй заявку на сайте и
                    мы с тобой свяжемся!</span
                  >
                </div>
                <div class="image">
                  <img src="@/assets/img/profs/design.png" alt="" />
                </div>
              </div>
            </slot>
          </div>

          <div class="modal-footer">
            <slot name="footer">
              <form action="https://talents.centrinvest.ru/">
                <MainButton class="modal-button" text="Хочу дальше!" />
              </form>
            </slot>
          </div>
        </div>
        <div v-else-if="prof === 'ds'" class="modal-container">
          <div class="modal-header">
            <slot name="header">
              <h3>Вам больше всего подходит профессия:</h3>
              <h2>Data scientist</h2>
            </slot>
          </div>

          <div class="modal-body">
            <slot name="body">
              <div class="body-wrapper">
                <div class="description">
                  <h4>Чем занимаются аналитики больших данных?</h4>
                  <p>
                    О, ты Data Scientist? Уф, садись поудобнее, сейчас будет
                    жаришка! Data Science - наука о работе с данными, это не
                    просто новое модное слово в мире IT! Профессия набирает
                    обороты даже быстрее, чем в свое время менеджер или юрист.
                    На самом деле, Data Science уже меняет мир, свидетельство
                    тому – множество стартапов в области больших данных и
                    искусственного интеллекта. Если ты хочешь стать частичкой
                    истории, то тебе точно сюда :)
                  </p>
                  <span
                    >Хочешь развиваться в этой теме? Оставляй заявку на сайте и
                    мы с тобой свяжемся!</span
                  >
                </div>
                <div class="image">
                  <img src="@/assets/img/profs/ds.png" alt="" />
                </div>
              </div>
            </slot>
          </div>

          <div class="modal-footer">
            <slot name="footer">
              <form action="https://talents.centrinvest.ru/">
                <MainButton class="modal-button" text="Хочу дальше!" />
              </form>
            </slot>
          </div>
        </div>
        <div v-else class="modal-container">
          <div class="modal-header">
            <slot name="header">
              <h3>Вам больше всего подходит профессия:</h3>
              <h2>GameDev</h2>
            </slot>
          </div>

          <div class="modal-body">
            <slot name="body">
              <div class="body-wrapper">
                <div class="description">
                  <h4>Чем занимаются разработчики игр?</h4>
                  <p>
                    Если вы своего рода художник, то вам сюда :) Играть в игры —
                    это интересно, а создавать игры — ещё круче. Задача
                    программиста в геймдев-сфере такая же, как и в любом другом
                    проекте – написать код. Благодаря ему пользователи могут
                    перемещаться по виртуальному миру, выполнять задания и
                    достигать целей игры. А главное, получать удовольствие!
                    Возможно, именно ТВОЯ будущая игра сделает кого-то
                    счастливее :)
                  </p>
                  <span
                    >Хочешь развиваться в этой теме? Оставляй заявку на сайте и
                    мы с тобой свяжемся!</span
                  >
                </div>
                <div class="image">
                  <img src="@/assets/img/profs/gamedev.png" alt="" />
                </div>
              </div>
            </slot>
          </div>

          <div class="modal-footer">
            <slot name="footer">
              <form action="https://talents.centrinvest.ru/">
                <MainButton class="modal-button" text="Хочу дальше!" />
              </form>
            </slot>
          </div>
        </div>
      </div>
    </div>
  </transition>
</template>

<script>
import MainButton from "@/components/MainButton";
export default {
  name: "MainModal",
  props: ["prof"],
  data() {
    return {};
  },
  components: {
    MainButton,
  },
  setup() {},
};
</script>

<style lang="scss" scoped>
.modal-enter-active,
.modal-leave-active {
  transition: opacity 0.7s ease;
}

.modal-enter-from,
.modal-leave-to {
  opacity: 0;
}

//modal

.modal-mask {
  position: absolute;
  z-index: 9998;
  top: 0;
  left: 0;
  width: 100%;
  height: 102vh;
  background-color: rgba(0, 0, 0, 0.5);
  display: table;
}

.modal-wrapper {
  display: table-cell;
  vertical-align: middle;
}

.modal-container {
  width: 80vw;
  margin: 0px auto;
  padding: 20px 30px;
  background: #d1ea9c;
  box-shadow: -4px 8px 8px 8px rgba(0, 0, 0, 0.25);
  border-radius: 8px;
}

.modal-header h3 {
  font-size: 2rem;
  margin-top: 0;
  color: black;
  text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  text-align: center;
}

.modal-header h2 {
  font-size: 4rem;
  margin-top: 30px;
  color: black;
  text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  text-align: center;
}

.modal-body {
  margin: 20px 0;
  text-align: center;
}

.modal-footer {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.modal-button {
  display: block;
  margin-top: 1rem;
  text-align: center;
}

.body-wrapper {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
}

.description {
  text-align: left;

  & h4 {
    font-size: 2rem;
  }

  & p {
    margin: 4vh 0;
    font-size: 1.5rem;
  }

  & span {
    font-style: italic;
    font-size: 1rem;
  }
}

.image img {
  width: 25vw;
}

@media (max-width: 600px) {
  .modal-header h3 {
    font-size: 1rem;
  }

  .modal-header h2 {
    font-size: 2rem;
  }

  .body-wrapper {
    flex-direction: column;
  }

  .description {
    text-align: center;

    & h4 {
      font-size: 1.2rem;
    }

    & p {
      margin: 2vh 0;
      font-size: 1.1rem;
    }

    & span {
      font-style: italic;
      font-size: 0.9rem;
    }
  }

  .image img {
    width: 70vw;
  }
}
</style>