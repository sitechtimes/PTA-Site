<template>
  <div>
    <div>
      <section class="topComponent">
        <div class="leftComponent">
          <h1 class="heading" ref="heading">Wall of Gratitude</h1>
          <div ref="sheading" class="thanks">
            <h2>Thank You!</h2>
            <p class="text">
              As you may know, in 2003 the Chancellor created the position of
              Parent Coordinator in all of the public schools in New York City.
              One of my roles is to be your parent advocate here at Tech and to
              actively facilitate a strong and productive relationship between
              the parents and school. Additionally, welcoming parents to a warm
              and friendly learning environment will provide an arena to share
              academic concerns related to your child's education. Staying
              informed can help your family adjust to the high school
              experience. Many challenges take place during these four years and
              will no doubt impact your lives and influence behavior. The Tech
              family is here to assist you in any way possible. Please utilize
              the resources available to help you in the process. As you come
              into the building I am making a point to greet you and check to
              see that your concerns are being addressed to your satisfaction.
              Please feel free to stop by and share what's on your mind. I look
              forward to meeting with you!
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
              <div
                v-for="item in filteredWall"
                :key="item"
                class="donationComponent"
              >
                <!-- should figure out how to make a component  -->
                <div
                  class="gratitudeImg"
                  :style="{
                    'background-image': 'url(' + item.image + ')',
                  }"
                ></div>
                <div>
                  <h6>{{ item.name }}</h6>
                  <p>thanks!</p>
                </div>
              </div>
            </div>
          </div>

          <div class="showArchive" ref="showArchive" @click="show = !show">
            <div v-if="show"><button class="btn">&#62;</button></div>
            <div v-else>
              <button class="btn">&#60;</button>
              <div class="archive" ref="archive">
                <h3>Archive</h3>
                <div class="yearsContainer">
                  <div class="years">
                    <div
                      class="year"
                      v-for="item in yearsShown"
                      @click="changeYr(item), filterArr(item)"
                      :key="item"
                    >
                      <h4>{{ item }}</h4>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
    </div>
    <NewFooter />
  </div>
</template>

<script>
import { gsap } from "gsap";
export default {
  mounted() {
    const { heading } = this.$refs;
    const { sheading } = this.$refs;
    const { img } = this.$refs;
    const { showArchive } = this.$refs;
    gsap.from(heading, { delay: 0.2, duration: 1, y: 100, opacity: 0 });
    gsap.from(sheading, { delay: 0.2, duration: 1, y: 100, opacity: 0 });
    gsap.from(img, { delay: 0.2, duration: 1, y: 100, opacity: 0 });
    gsap.from(showArchive, { delay: 0.2, duration: 1, y: 100, opacity: 0 });
    this.filterArr();
    this.getYears();
    this.removewithfilter(this.years);
  },

  data() {
    return {
      show: false,
      currentYear: new Date().getFullYear(),
      // years: [2023, 2022, 2021],
      years: [],
      yearsShown: [],
      filteredWall: [],
      wall: [
        {
          year: "2023",
          name: "Cool Parent 9",
          image:
            "https://m.media-amazon.com/images/I/61yknJ33qhL._AC_UF1000,1000_QL80_.jpg",
        },
        {
          year: "2023",
          name: "Cool Parent 8",
          image:
            "https://cdn.drawception.com/images/panels/2016/2-22/DPPYntPAjm-2.png",
        },
        {
          year: "2022",
          name: "Cool Parent 7",
          image:
            "https://c8.alamy.com/comp/2NH1J1C/marine-seagull-icon-cartoon-vector-sea-bird-cute-animal-2NH1J1C.jpg",
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
          image:
            "https://www.pngitem.com/pimgs/m/6-65873_seagull-illustration-png-seagull-clipart-transparent-png.png",
        },
        {
          year: "2021",
          name: "Cool Parent 3",
          image:
            "https://hdclipartall.com/images/cartoon-seagull-clipart-seagulls-clipart-1606_1476.jpg",
        },
        {
          year: "2021",
          name: "Cool Parent 2",
          image:
            "https://www.pngitem.com/pimgs/m/6-65873_seagull-illustration-png-seagull-clipart-transparent-png.png",
        },
        {
          year: "2021",
          name: "Cool Parent 1",
          image:
            "https://creazilla-store.fra1.digitaloceanspaces.com/cliparts/10342/gull-clipart-xl.png",
        },
      ],
    };
  },
  methods: {
    changeYr: function (e) {
      this.currentYear = e;
      console.log(this.currentYear);
    },
    filterArr: function () {
      this.filteredWall = this.wall.filter(
        (item) => item.year == this.currentYear
      );
    },
    getYears: function () {
      for (let i = 0; i < this.wall.length; i++) {
        this.years.push(this.wall[i].year);
      }
      console.log(this.years);
    },
    removewithfilter: function (arr) {
      this.yearsShown = arr.filter(function (v, i, self) {
        // It returns the index of the first
        // instance of each value
        return i == self.indexOf(v);
      });
      console.log(this.yearsShown);
      return this.yearsShown;
    },
  },
};
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
#gradient {
  width: 100%;
  padding: 0%;
  position: absolute;
  top: 0%;
  left: 0%;
  height: 80rem;
  z-index: -5;
  background: linear-gradient(
    180deg,
    #feb89a 0%,
    #fdd8b8 18%,
    #ffecc5 40%,
    #faf2e1 75%,
    #faf2e1 80%,
    #fff 95%
  );
  overflow-x: hidden;
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
.arrayCon {
  display: flex;
  flex-direction: column;
}
.bottomCon {
  display: flex;
  flex-direction: row;
  justify-content: center;
}
.showArchive {
  left: 0%;
  position: absolute;
}
.archive {
  width: 19rem;
  height: 33rem;
  font-family: "Kumbh Sans", san serif;
  font-weight: 800;
  color: #483221;
  text-align: center;
  background: white;
  padding: 1rem 0rem 1rem 1rem;
  border-radius: 1rem;
}
.years {
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 33rem;
  overflow-y: auto;
  scrollbar-width: none;
}

.year {
  margin: 5px;
  width: 16rem;
  height: 4rem;
  background-color: #fcf6e9;
  border-radius: 1rem;
  transition: 0.5s;
}
.year:hover {
  background-color: #643935;
  color: white;
  cursor: pointer;
}
.btn {
  padding: 0.5rem 1.5rem 0.5rem 1.5rem;
  position: absolute;
  left: 0%;
  margin-left: 81.5%;
  transition: all 1s ease-in;
}
h3 {
  font-size: 3rem;
  margin: 1rem 0;
}
h4 {
  font-size: 1.4rem;
  margin: 7%;
}
h6 {
  font-size: 1.4rem;
  margin: 7%;
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
@media screen and (max-width: 1850px) {
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
  .archive {
    width: 14rem;
    height: 20rem;
    font-family: "Kumbh Sans", san serif;
    font-weight: 800;
    color: #483221;
    text-align: center;
  }
  .btn {
    margin-left: 75%;
  }
  .years {
    display: flex;
    flex-direction: column;
    align-items: center;
    height: auto;
    overflow-y: scroll;
    scrollbar-width: none;
  }
  .year {
    margin: 5px;
    width: 12rem;
    height: 3.5rem;
    background-color: #fcf6e9;
    border-radius: 1.5rem;
    transition: 0.5s;
  }
  .year:hover {
    background-color: #643935;
    color: white;
    cursor: pointer;
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
@media screen and (max-width: 576px) {
  .topComponent {
    display: flex;
    flex-direction: column;
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
  h4 {
    font-size: 1rem;
  }
  .archive {
    width: 10rem;
    height: 18rem;
  }
  .year {
    width: 8rem;
    border-radius: 1rem;
    height: 2.5rem;
  }
  .btn {
    padding: 0.4rem 1.2rem 0.4rem 1.2rem;
  }
}
@media screen and (max-width: 500px) {
  .gratitudeImg {
    width: 10rem;
    height: 13rem;
  }
}
</style>
