<template>
<transition name=fade>
  <div class="modal-mask">
    <div class="modal-wrapper">
      <div class="modal-container">
        <div class="modal-header">
          <slot name="header">
            <h3>Внимание вопрос</h3>
          </slot>
        </div>

        <div class="modal-body">
          <slot name="body">
				{{question.text}}
          </slot>
        </div>

        <div class="modal-footer">
          <slot name="footer">
            <form>
              <label>
                <input type="radio" name="radio" value=1 v-model='picked' />
                <span>Нет, это не так</span>
              </label>
              <label>
                <input type="radio" name="radio" value=2 v-model='picked' />
                <span>Скорее нет</span>
              </label>
              <label>
                <input type="radio" name="radio" value=3 checked v-model='picked' />
                <span>Не знаю</span>
              </label>
              <label>
                <input type="radio" name="radio" value=4 v-model='picked' />
                <span>Пожалуй так</span>
              </label>
              <label>
                <input type="radio" name="radio" value=5 v-model='picked' />
                <span>Совершенно верно</span>
              </label>
            </form>
            <MainButton class="modal-button" text="Отправить" @click="$emit('close', [picked, question.prof])" />
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
  name: 'MainModal',
  props: {
	  question: Object,
  },
  data() {
	  return {
		  picked: -1,
	  }
  },
  components: {
    MainButton,
  },
  setup() {},
};
</script>

<style lang="scss" scoped>
//modal

.modal-mask {
  position: fixed;
  z-index: 9998;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
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
  background: #D1EA9C;
	box-shadow: -4px 8px 8px 8px rgba(0, 0, 0, 0.25);
	border-radius: 8px;
  font-family: Helvetica, Arial, sans-serif;
}

.modal-header h3 {
  margin-top: 0;
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

.modal-enter-active,
.modal-leave-active {
  transition: opacity 0.5s ease;
}

.modal-enter-from,
.modal-leave-to {
  opacity: 0;
}


//radio btns
*,
*:after,
*:before {
  box-sizing: border-box;
}

$primary-color: #125A57;
$text-color: mix(#000, $primary-color, 64%);

body {
  font-family: "Open Sans", sans-serif;
  color: $text-color;
  font-size: calc(1em + 1.25vw);
  background-color: mix(#fff, $primary-color, 90%);
}

form {
  display: flex;
  flex-wrap: wrap;
  flex-direction: row;
  justify-content: center;
}

label {
  display: flex;
  cursor: pointer;
  font-weight: 500;
  position: relative;
  overflow: hidden;
  margin: 1vh 1vw;
  /* Accessible outline */
  /* Remove comment to use */
  /*
		&:focus-within {
				outline: .125em solid $primary-color;
		}
	*/
  input {
    position: absolute;
    left: -9999px;
    &:checked + span {
      background-color: rgba($color: #4E8A4B, $alpha: .4);
      &:before {
        box-shadow: inset 0 0 0 0.4375em $primary-color;
      }
    }
  }
  span {
    display: flex;
    align-items: center;
    padding: 0.375em 0.75em 0.375em 0.375em;
    border-radius: 99em; // or something higher...
    transition: 0.25s ease;
    &:hover {
      background-color: rgba($color: #4E8A4B, $alpha: .3);
    }
    &:before {
      display: flex;
      flex-shrink: 0;
      content: "";
      background-color: #fff;
      width: 1.5em;
      height: 1.5em;
      border-radius: 50%;
      margin-right: 0.375em;
      transition: 0.25s ease;
      box-shadow: inset 0 0 0 0.125em $primary-color;
    }
  }
}

</style>