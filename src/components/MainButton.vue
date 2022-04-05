<template>
  <button class="btn">
    {{ this.text }}
    <!-- <span class="blob-btn__inner">
      <span class="blob-btn__blobs">
        <span class="blob-btn__blob"></span>
        <span class="blob-btn__blob"></span>
        <span class="blob-btn__blob"></span>
        <span class="blob-btn__blob"></span>
      </span>
    </span> -->
  </button>
</template>

<script>
export default {
  name: "MainButton",
  props: ["text"],
  setup() {},
};
</script>

<style lang="scss" scoped>
*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
$openSans: "Open Sans", Helvetica, Arial, sans-serif;

// $green: #96DC92;
// $yellow: #FFF32A;
// $borderW: 0px;

// .blob-btn {
//   $numOfBlobs: 1;
//   z-index: 1;
//   position: relative;
//   padding: 20px 46px;
//   margin: 30px auto;
//   text-align: center;
//   text-transform: uppercase;
//   color: black;
//   font-size: 16px;
//   font-weight: bold;
//   background-color: transparent;
//   outline: none;
//   border: none;
//   transition: color 0.5s;
//   cursor: pointer;
//   border-radius:32px;
//   box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);

//   &:before {
//     content: "";
//     z-index: 1;
//     position: absolute;
//     left: 0;
//     top: 0;
//     width: 100%;
//     height: 100%;
//     border: $borderW solid $green;
//     border-radius:30px;
//   }

//   &:after {
//     content: "";
//     z-index: -2;
//     position: absolute;
//     left: $borderW*1.5;
//     top: $borderW*1.5;
//     width: 100%;
//     height: 100%;

//     transition: all 0.3s 0.2s;
//     border-radius:30px;
//   }

//   &:hover {
//     color: $yellow;
//     border-radius:30px;

//     &:after {
//       transition: all 0.3s;
//       left: 0;
//       top: 0;
//       border-radius:30px;
//     }
//   }

//   &__inner {
//     z-index: -1;
//     overflow: hidden;
//     position: absolute;
//     left: 0;
//     top: 0;
//     width: 100%;
//     height: 100%;
//     border-radius:30px;
//     background:$yellow;
//   }

//   // additional container created, because in FF blobs are breaking overflow:hidden of element with svg gooey filter
//   &__blobs {
//     position: relative;
//     display: block;
//     height: 100%;
//     filter: url('#goo');
//   }

//   &__blob {
//     position: absolute;
//     top: $borderW;
//     width: 100% / $numOfBlobs;
//     height: 100%;
//     background: $green;
//     border-radius: 100%;
//     transform: translate3d(0,150%,0) scale(1.7);
//     transition: transform 0.45s;

//     @supports(filter: url('#goo')) {
//       transform: translate3d(0,150%,0) scale(1.4);
//     }

//     @for $i from 1 through $numOfBlobs {
//       &:nth-child(#{$i}) {
//         left: ($i - 1) * (120% / $numOfBlobs);
//         transition-delay: ($i - 1) * 0.08s;
//       }
//     }

//     .blob-btn:hover & {
//       transform: translateZ(0) scale(1.7);

//       @supports(filter: url('#goo')) {
//         transform: translateZ(0) scale(1.4);
//       }
//     }
//   }

// }

// .button {
//   font: $openSans;
//   font-size: 16px;
//   font-weight: 200;
//   letter-spacing: 1px;
//   padding: 13px 20px 13px;
//   outline: 0;
//   border: 1px solid #1C7817;
//   cursor: pointer;
//   position: relative;
//   background-color: rgba(0, 0, 0, 0);
//   user-select: none;
//   -webkit-user-select: none;
//   touch-action: manipulation;
//   border-radius: 4px;

//   margin: 30px auto;
// }

// .button:after {
//   content: "";
//   background-color: #FFF32A;
//   border-radius: 4px;
//   width: 100%;
//   z-index: -1;
//   position: absolute;
//   height: 100%;
//   top: 7px;
//   left: 7px;
//   transition: 0.2s;
// }

// .button:hover:after {
//   top: 0px;
//   left: 0px;
// }

// @media (min-width: 768px) {
//   .button {
//     padding: 13px 50px 13px;
//   }
// }

.btn {
  font: $openSans;
  box-sizing: border-box;
  appearance: none;
  background-color: #fff32a;
  border: 1px solid #fff32a;
  border-radius: 32px;
  color: white;
  cursor: pointer;
  display: flex;
  align-self: center;
  font-size: 1rem;
  font-weight: 400;
  line-height: 1;
  margin: 30px;
  padding: 1.2em 2.8em;
  text-decoration: none;
  text-align: center;
  text-transform: uppercase;
  font-weight: 700;

  border-color: #fff32a;
  color: black;
  background: {
    image: linear-gradient(45deg, #4EB848 50%, transparent 50%);
    position: 100%;
    size: 400%;
  }
  transition: all 0.5s ease-in-out;

  &:hover {
    background-position: 0;
  }

  &:hover,
  &:focus {
    color: #fff32a;
    outline: 0;
  }
}
</style>