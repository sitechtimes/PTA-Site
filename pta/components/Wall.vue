<template>
  <div>
    <div>
      <section class="topComponent">
        <div class="leftComponent">
          <h1 class="heading" ref="heading">Wall of Gratitude</h1>
          <div ref="sheading" class="thanks">
            <h2>Thank You!</h2>
            <p class="text">
              As you may know, in 2003 the Chancellor created the position of Parent Coordinator in all of the public
              schools in New York City. One of my roles is to be your parent advocate here at Tech and to actively
              facilitate a strong and productive relationship between the parents and school. Additionally, welcoming
              parents to a warm and friendly learning environment will provide an arena to share academic concerns
              related to your child's education. Staying informed can help your family adjust to the high school
              experience. Many challenges take place during these four years and will no doubt impact your lives and
              influence behavior. The Tech family is here to assist you in any way possible. Please utilize the
              resources available to help you in the process. As you come into the building I am making a point to greet
              you and check to see that your concerns are being addressed to your satisfaction. Please feel free to stop
              by and share what's on your mind. I look forward to meeting with you!
            </p>
            <div class="contactInfoDiv">
              <p class="contactInfo">Sincerely, Barbara Malenfant</p>
              <p class="contactInfo">bmalenfant@schools.nyc.gov</p>
              <p class="contactInfo">347-563-4563</p>
            </div>
          </div>
        </div>
        <div class="middlemobile">
          <div class="image" ref="img"></div>
        </div>
      </section>
      <section class="bottomComponent">
        <div class="bottomCon">
          <div class="donationGradient"></div>
          <div class="arrayCon">
            <h2>― •{{ currentYear }}• ―</h2>
            <div class="donationArray">
              <div v-for="item in filteredWall" :key="item" class="donationComponent">
                <!-- should figure out how to make a component  -->
                <div
                  class="gratitudeImg"
                  :style="{
                    'background-image': 'url(' + item.image + ')',
                  }"
                ></div>
                <div>
                  <h6>{{ item.name }}</h6>
                  <p class="note">Thank you!</p>
                </div>
              </div>
            </div>
          </div>

          <div class="archiveCon" ref="archiveCon">
            <div class="archivehead">
              <h3 class="archive">Archive</h3>

              <button
                class="showBtn"
                @click="
                  up = !up;
                  show = !show;
                "
              >
                <svg v-if="up" class="downArrow" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512">
                  <!-- Font Awesome Free 6.5.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2024 Fonticons, Inc. -->
                  <path
                    fill="#ffffff"
                    d="M233.4 406.6c12.5 12.5 32.8 12.5 45.3 0l192-192c12.5-12.5 12.5-32.8 0-45.3s-32.8-12.5-45.3 0L256 338.7 86.6 169.4c-12.5-12.5-32.8-12.5-45.3 0s-12.5 32.8 0 45.3l192 192z"
                  />
                </svg>
                <div v-else>
                  <svg class="downArrow" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512">
                    <!-- Font Awesome Free 6.5.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2024 Fonticons, Inc. -->
                    <path
                      fill="#ffffff"
                      d="M233.4 105.4c12.5-12.5 32.8-12.5 45.3 0l192 192c12.5 12.5 12.5 32.8 0 45.3s-32.8 12.5-45.3 0L256 173.3 86.6 342.6c-12.5 12.5-32.8 12.5-45.3 0s-12.5-32.8 0-45.3l192-192z"
                    />
                  </svg>
                </div>
              </button>
            </div>
            <div class="hline"></div>

            <div v-if="show" class="yearsContainer">
              <div class="years">
                <div class="year" v-for="item in yearsShown" @click="changeYr(item), filterArr(item)" :key="item">
                  <h4>{{ item }}</h4>
                </div>
              </div>
            </div>
            <div v-else></div>
          </div>
        </div>
      </section>
    </div>
    <Footer />
  </div>
</template>

<script setup>
import { gsap } from "gsap";

const heading = ref();
const sheading = ref();
const img = ref();
const archiveCon = ref();

onMounted(() => {
  gsap.from(heading, { delay: 0.2, duration: 1, y: 100, opacity: 0 });
  gsap.from(sheading, { delay: 0.2, duration: 1, y: 100, opacity: 0 });
  gsap.from(img, { delay: 0.2, duration: 1, y: 100, opacity: 0 });
  gsap.from(archiveCon, { delay: 0.2, duration: 1, y: 100, opacity: 0 });
  filterArr();
  getYears();
  removewithfilter(years.value);
});

const up = ref(false);
const show = ref(true);
const currentYear = ref(new Date().getFullYear());

const years = ref([]);
const yearsShown = ref([]);
const filteredWall = ref([]);
const wall = ref([
  {
    year: "2023",
    name: "Cool Parent 9",
    image: "https://m.media-amazon.com/images/I/61yknJ33qhL._AC_UF1000,1000_QL80_.jpg",
  },
  {
    year: "2023",
    name: "Cool Parent 8",
    image: "https://cdn.drawception.com/images/panels/2016/2-22/DPPYntPAjm-2.png",
  },
  {
    year: "2022",
    name: "Cool Parent 7",
    image: "https://c8.alamy.com/comp/2NH1J1C/marine-seagull-icon-cartoon-vector-sea-bird-cute-animal-2NH1J1C.jpg",
  },
  {
    year: "2022",
    name: "Cool Parent 6",
    image: "https://clipart-library.com/img1/843122.png",
  },
  {
    year: "2022",
    name: "Cool Parent 5",
    image:
      "https://img.freepik.com/premium-photo/seagull-sneakers-panama-watercolor-illustration-summer-clipart-with-cartoon-character_647110-29.jpg?w=826",
  },
  {
    year: "2022",
    name: "Cool Parent 4",
    image: "https://www.pngitem.com/pimgs/m/6-65873_seagull-illustration-png-seagull-clipart-transparent-png.png",
  },
  {
    year: "2021",
    name: "Cool Parent 3",
    image: "https://hdclipartall.com/images/cartoon-seagull-clipart-seagulls-clipart-1606_1476.jpg",
  },
  {
    year: "2021",
    name: "Cool Parent 2",
    image: "https://www.pngitem.com/pimgs/m/6-65873_seagull-illustration-png-seagull-clipart-transparent-png.png",
  },
  {
    year: "2021",
    name: "Cool Parent 1",
    image: "https://creazilla-store.fra1.digitaloceanspaces.com/cliparts/10342/gull-clipart-xl.png",
  },
]);

function changeYr(e) {
  currentYear.value = e;
  console.log(currentYear.value);
}
function filterArr() {
  filteredWall.value = wall.value.filter((item) => item.year == currentYear.value);
}
function getYears() {
  for (let i = 0; i < wall.value.length; i++) {
    years.value.push(wall.value[i].year);
  }
  console.log(years.value);
}
function removewithfilter(arr) {
  yearsShown.value = arr.filter(function (v, i, self) {
    // It returns the index of the first
    // instance of each value
    return i == self.indexOf(v);
  });
  console.log(yearsShown.value);
  return yearsShown.value;
}
</script>

<style scoped>
@import url(../assets/base.css);
.text {
  font-size: 1.3rem;
  margin-top: 1rem;
  line-height: 1.8rem;
}
h2 {
  margin: 0;
  margin-left: 0;
  font-size: 2.4rem;
}
.topComponent {
  display: flex;
  flex-direction: row;
  margin: 0 7% 0 7%;
  justify-content: space-between;
}
.heading {
  margin-left: 0;
}
.thanks {
  font-family: "Kumbh Sans", san serif;
  font-weight: 400;
  font-size: 1.15rem;
  margin-top: 1.1rem;
  color: #483221;
  width: 45rem;
}
.image {
  margin: 25% 0 0 0%;
  width: 500px;
  height: 500px;
  border-radius: 50%;
  background-image: url(https://cdnb.artstation.com/p/assets/images/images/052/438/797/large/paul-seagull-compositing-9.jpg?1659794101);
  background-repeat: no-repeat;
  background-size: cover;
}
.note {
  margin-top: 0.2rem;
}
.arrayCon {
  display: flex;
  flex-direction: column;
}
.donationArray::-webkit-scrollbar {
  width: 15px;
}

.donationArray::-webkit-scrollbar-track {
  background: #483221;
  border-radius: 8px;
}
.donationArray::-webkit-scrollbar-thumb {
  border-radius: 100px;
  background: white;
  width: 5px;
  border: 3px solid transparent;
  background-clip: content-box;
}
.bottomCon {
  display: flex;
  flex-direction: row;
  justify-content: center;
}
.archiveCon {
  left: 0%;
  position: absolute;
}

.archivehead {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  padding: 0 0.5rem 0 0.5rem;
}
.hline {
  height: 0.05rem;
  width: 15rem;
  background: white;
  margin-left: auto;
  margin-right: auto;
}

.archiveCon {
  width: 15rem;
  font-family: "Kumbh Sans", san serif;
  font-weight: 800;
  color: #fff;
  text-align: center;
  background: var(--text-color);
  padding: 0.2rem 1.2rem 1.2rem 1.2rem;
  border-radius: 1rem;
}
.downArrow {
  width: 2rem;
  height: 2rem;
  margin-top: 0.6rem;
  /* padding-top: 0.6rem; */
}

.yearsContainer {
  display: block;
  overflow-y: scroll;
  margin-top: 1rem;
}

.yearsContainer::-webkit-scrollbar {
  width: 15px;
}

.yearsContainer::-webkit-scrollbar-track {
  background: white;
  border-radius: 8px;
}
.yearsContainer::-webkit-scrollbar-thumb {
  border-radius: 100px;
  background: #483221;
  width: 5px;
  border: 3px solid transparent;
  background-clip: content-box;
}

.showBtn:active .yearsContainer {
  display: block;
}
.years {
  display: flex;
  flex-direction: column;
  height: 20vw;
}

.year {
  width: 90%;
  border-radius: 0.8rem;
  margin-top: 1rem;
  padding-top: 0.5rem;
  padding-bottom: 0.5rem;
  padding-left: 0.8rem;
  transition: 0.5s;
}
.year:hover {
  background-color: #fff;
  color: var(--text-color);
  cursor: pointer;
  padding-left: 1rem;
}
.showBtn {
  background: none;
  border: none;
  padding: 0;
}
.showBtn:hover {
  cursor: pointer;
}
h3 {
  font-size: 2.5rem;
  margin: 1rem 0;
}
.archive {
  margin-top: 1rem;
  margin-bottom: 0.6rem;
}
h4 {
  font-size: 1.8rem;
  font-weight: 600;
  margin: 0;
  text-align: left;
}
h6 {
  font-size: 1.4rem;
  margin-top: 0.8rem;
  margin-bottom: 0rem;
  width: max-content;
}
.contactInfo {
  margin: 0.2rem;
  margin-left: 0;
  text-align: right;
}
.contactInfoDiv {
  margin-top: 1.5rem;
}
.bottomComponent {
  font-family: "Kumbh Sans", san serif;
  margin-top: 10rem;
  color: #483221;
  text-align: center;
}
.donationArray {
  width: 95vw;
  margin: auto;
  display: flex;
  justify-content: space-evenly;
  text-align: center;
  flex-wrap: wrap;
  overflow-x: hidden;
  margin-top: 4rem;
  margin-bottom: 8rem;
  height: 47rem;
}
.donationGradient {
  position: absolute;

  width: 92vw;
  margin-top: 40rem;
  height: 10rem;
}
.donationComponent {
  margin: 15px 0;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.gratitudeImg {
  border-radius: 15px;
  border: #483221 solid 3px;
  width: 18rem;
  height: 21rem;
  /* background-image: url(https://www.ptopmiami.org/wp-content/uploads/2020/11/child-hugging-father.jpg); */
  background-size: cover;
}

@media screen and (max-width: 1500px) {
  .donationGradient {
    position: absolute;
    width: 92vw;
    margin-top: 35rem;
    height: 2rem;
  }
  .heading {
    margin: 8% 0% 0% 0%;
  }
  .donationComponent {
    margin: 15px 0;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .gratitudeImg {
    border-radius: 20px;
    border: #483221 solid 3px;
    width: 15rem;
    height: 18rem;
    background-size: cover;
  }
  .leftComponent {
    margin-right: 0;
  }
  h2 {
    font-size: 2rem;
  }
  .thanks {
    font-family: "Kumbh Sans", san serif;
    font-weight: 400;
    font-size: 1rem;
    margin-top: 1rem;
    color: #483221;
    width: 40rem;
  }
  h3 {
    font-size: 2rem;
    margin: 1rem 0;
  }
  .archiveCon {
    width: 12rem;
  }
  .hline {
    width: 12rem;
  }
  .downArrow {
    width: 1.8rem;
    height: 1.8rem;
  }
  .year {
    margin-top: 0.4rem;
    margin-block: 0.4rem;
    padding-top: 0.3rem;
    padding-bottom: 0.3rem;
    width: 85%;
  }
  h4 {
    font-size: 1.6rem;
  }
  .text {
    font-size: 1rem;
    width: 90%;
    line-height: 1.6rem;
  }
  .contactInfo {
    font-size: 1rem;
    margin: 0.1rem;
    margin-left: 0;
    text-align: right;
    width: 90%;
  }
  .contactInfoDiv {
    margin-top: 1.2rem;
  }
  .image {
    margin: 25% 0 0 0%;
    width: 450px;
    height: 450px;
  }
}
@media screen and (max-width: 1200px) {
  .heading {
    margin: 6% 0 0 0%;
  }
  .donationArray {
    width: 70vw;
  }
  .image {
    margin: 40% 0 0 0%;
    width: 350px;
    height: 350px;
  }
  .thanks {
    width: 32rem;
  }
  .text {
    font-size: 0.95rem;
    line-height: 1.4rem;
  }
  .years {
    height: 25vw;
  }
}
@media only screen and (max-width: 992px) {
  .thanks {
    width: 100%;
  }
  .contactInfo {
    width: 100%;
  }
  .text {
    width: 100%;
  }
  .image {
    display: none;
  }
  .bottomComponent {
    margin-top: 5rem;
  }
}
@media only screen and (max-width: 768px) {
  .donationArray {
    margin-top: 5rem;
  }
  .archiveCon {
    margin-top: 2rem;
    width: 11rem;
    height: auto;
  }
  .hline {
    width: 10.5rem;
  }
  .downArrow {
    width: 1.8rem;
    height: 1.8rem;
  }
  .archive {
    font-size: 1.8rem;
  }
  h4 {
    font-size: 1.4rem;
  }
  .years {
    height: 30vw;
  }
}
@media screen and (max-width: 576px) {
  .topComponent {
    display: flex;
    flex-direction: column;
  }
  h2 {
    font-size: 1.5rem;
  }
  .image {
    margin: 8% 0 0 5%;
    width: 200px;
    height: 200px;
    border-radius: 50%;
    background-image: url(https://cdnb.artstation.com/p/assets/images/images/052/438/797/large/paul-seagull-compositing-9.jpg?1659794101);
    background-repeat: no-repeat;
    background-size: cover;
  }
  h3 {
    font-size: 1.5rem;
  }
  .yearsContainer::-webkit-scrollbar-thumb {
    width: 2px;
    border: 2px solid transparent;
  }

  .archiveCon {
    margin-top: 3rem;
    width: 10rem;
    height: auto;
    padding: 0.2rem 1rem 1rem 1rem;
  }
  .archive {
    margin-top: 0.8rem;
    margin-bottom: 0.5rem;
  }
  .hline {
    width: 8.5rem;
  }
  .downArrow {
    width: 1.4rem;
    height: 1.4rem;
  }
  h4 {
    font-size: 1.2rem;
  }
  .years {
    height: 10rem;
  }
}
@media screen and (max-width: 500px) {
  .gratitudeImg {
    width: 10rem;
    height: 13rem;
  }
}
</style>
