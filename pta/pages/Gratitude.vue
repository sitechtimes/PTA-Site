<template>
  <div>
    <div id="gradient"></div>
    <div>
      <section class="topComponent">
        <div class="leftComponent">
          <h1 class="heading" ref="heading">Wall of Gratitude</h1>
          <div class="thanks">
            <h2>Thank You!</h2>
            <p>
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
          </div>
        </div>
        <div class="image"></div>
        <div class="archive">
          <h3>Archive</h3>
          <div class="yearsContainer">
            <div class="years">
              <div
                class="year"
                v-for="item in gratitudeArr"
                @click="changeYr(item), changeImg(item)"
                :key="item"
              >
                <h4>{{ item.year }}</h4>
              </div>
            </div>
          </div>
        </div>
      </section>
      <section class="bottomComponent">
        <h5>― •{{ currentYear }}• ―</h5>
        <div class="donationGradient"></div>
        <div class="donationArray">
          <div v-for="img in currentImg" :key="img" class="donationComponent">
            <div
              class="gratitudeImg"
              :style="{
                'background-image': 'url(' + img + ')', //breaks code
              }"
            ></div>
            <div>
              <!-- <h6>{{ item.name }}</h6> how do i iterate through 2 arrays in the same component?? can i? -->
              <h7>thanks!</h7>
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
    gsap.from(heading, { delay: 0, duration: 1, y: 100, opacity: 0 });
  },

  data() {
    return {
      currentImg: [], //make it display images from the current yr.
      currentYear: new Date().getFullYear(),
      gratitudeArr: [
        {
          year: "2023",
          name: ["Cool Paren 9", "Cool parent 8"],
          image: [
            "https://m.media-amazon.com/images/I/61yknJ33qhL._AC_UF1000,1000_QL80_.jpg",
            "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSnNtKKh4nTpZabj23BthUNWo9XWAYL63D8QaYtedn84Q&s",
          ],
        },

        {
          year: "2022",
          name: "Cool Paren 7",
          image: [
            "https://fanatics.frgimages.com/philadelphia-eagles/swoop-philadelphia-eagles-12-x-12-minimalist-mascot-poster-print_pi5135000_ff_5135432-ff27d0ef2846d226899d_full.jpg?_hv=2",
          ],
        },
        {
          year: "2021",
          name: "Cool Paren 6",
          image: [
            "https://t4.ftcdn.net/jpg/05/83/05/69/360_F_583056955_s7lX0lbcaQkhVKl8v0cFwxZsJmMokKIz.jpg",
          ],
        },
        {
          year: "2020",
          name: "Cool Paren 5",
          image: [
            "https://c8.alamy.com/comp/2NH1J1C/marine-seagull-icon-cartoon-vector-sea-bird-cute-animal-2NH1J1C.jpg",
          ],
        },
        {
          year: "2019",
          name: "Cool Paren 4",
          image: ["https://clipart-library.com/img1/843122.png"],
        },
        {
          year: "2018",
          name: "Cool Paren 3",
          image: [
            "https://hdclipartall.com/images/cartoon-seagull-clipart-seagulls-clipart-1606_1476.jpg",
          ],
        },
        {
          year: "2017",
          name: "Cool Paren 2",
          image: [
            "https://www.pngitem.com/pimgs/m/6-65873_seagull-illustration-png-seagull-clipart-transparent-png.png",
          ],
        },
        {
          year: "2016",
          name: "Cool Paren 1",
          image: [
            "https://img.freepik.com/premium-photo/seagull-sneakers-panama-watercolor-illustration-summer-clipart-with-cartoon-character_647110-29.jpg?w=826",
          ],
        },
      ],
    };
  },
  methods: {
    changeYr: function (e) {
      this.currentYear = e.year;
      console.log(this.currentYear);
    },
    changeImg: function (e) {
      this.currentImg.length = 0;
      this.currentImg.push(...e.image);
      console.log(...e.image);
    },
    filterArr: function (yr) {
      let currentYr = this.gratitudeArr.filter((years) =>
        this.gratitudeArr.includes(yr)
      );
      currentYr.forEach((years) => console.log(this.gratitudeArr.name));
    },
  },
};
</script>
<style scoped>
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
  margin: 0 0 0 8%;
}
.heading {
  font-family: "Kumbh Sans", san serif;
  font-weight: 800;
  font-size: 6rem;
  color: #483221;
  width: 33rem;
}
.thanks {
  font-family: "Kumbh Sans", san serif;
  font-weight: 400;
  font-size: 1.4rem;
  color: #483221;
  width: 40rem;
}
.image {
  margin: 4% 0 0 5%;
  width: 500px;
  height: 500px;
  border-radius: 50%;
  background-image: url(https://cdnb.artstation.com/p/assets/images/images/052/438/797/large/paul-seagull-compositing-9.jpg?1659794101);
  background-repeat: no-repeat;
  background-size: cover;
}
.archive {
  margin: 4% 0 0 5%;
  width: 19rem;
  height: 33rem;
  font-family: "Kumbh Sans", san serif;
  font-weight: 800;
  color: #483221;
  text-align: center;
}
.years {
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 33rem;
  overflow-y: scroll;
  scrollbar-width: none;
}

.year {
  margin: 5px;
  width: 16rem;
  height: 4rem;
  background-color: #fcf6e9;
  border-radius: 20px;
  transition: 0.5s;
}
.year:hover {
  background-color: #643935;
  color: white;
  cursor: pointer;
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
.bottomComponent {
  font-family: "Kumbh Sans", san serif;
  margin-top: 5rem;
  color: #483221;
  text-align: center;
}
h5 {
  width: max-content;
  margin: auto;
  font-size: 3rem;
}
.donationArray {
  width: 90vw;
  margin: auto;
  display: flex;
  justify-content: space-evenly;
  text-align: center;
  flex-wrap: wrap;
  overflow-x: hidden;
  margin-bottom: 8rem;
  height: 47rem;
}
.donationGradient {
  position: absolute;
  background: linear-gradient(
    180deg,
    rgba(255, 255, 255, 0) 0%,

    rgb(255, 255, 255) 100%
  );
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
</style>
