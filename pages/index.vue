<template>
  <div class="w-full container mx-auto">
    <!-- Hero section -->
    <section id="hero" class="w-full pb-24">
      <BaseSection>
        <div class="col-span-12 lg:col-span-6 mt-12 xl:mt-10 space-y-4 sm:space-y-6 px-4 text-center sm:text-left">
          <h1
            data-aos="fade-right"
            data-aos-once="true"
            class="text-[2.5rem] sm:text-5xl xl:text-6xl font-bold leading-tight capitalize sm:pr-8 xl:pr-10"
          >
            Optimize Your Time with <br> <span class="text-time-gradient">Time </span>
            <span class="text-minder-gradient">Minder</span>
          </h1>
          <p data-aos="fade-down" data-aos-once="true" data-aos-delay="300" class="paragraph hidden sm:block">
            Time Minder memastikan Anda dapat tetap fokus dan terorganisir dalam menyelesaikan tugas-tugas Anda setiap hari.
          </p>
          <div
            data-aos="fade-up"
            data-aos-once="true"
            data-aos-delay="700"
            class="flex flex-col sm:flex-row space-y-4 sm:space-y-0 sm:space-x-4 mt-4"
          >
            <BaseButton
              class="max-w-full px-8 py-4 bg-gradient-to-r from-[#FFBF1C] to-[#F8F097] text-white"
            >
              <NuxtLink to="/timer">Get Started</NuxtLink>
            </BaseButton>
            <BaseButton
              class="max-w-full px-6 py-4 bg-inherit text-gradient border border-[#FFBF1C] flex items-center justify-center"
            >
              <h4>Download App</h4>
            </BaseButton>
          </div>
        </div>
        <div class="hidden sm:block col-span-12 lg:col-span-6">
          <div class="w-full">
            <img
              data-aos="fade-up"
              data-aos-once="true"
              :src="require('~/assets/img/hero-image.svg')"
              class="mt-2"
              alt=""
            />
          </div>
        </div>
        <img
          data-aos="fade-up"
          data-aos-delay="300"
          :src="require('~/assets/img/pattern/ellipse-1.png')"
          class="hidden sm:block absolute bottom-12 xl:bottom-16 left-4 xl:left-0 w-6"
        />
        <img
          data-aos="fade-up"
          data-aos-delay="300"
          :src="require('~/assets/img/pattern/ellipse-2.png')"
          class="hidden sm:block absolute top-4 sm:top-10 right-64 sm:right-96 xl:right-[32rem] w-6"
        />
        <img
          data-aos="fade-up"
          data-aos-delay="300"
          :src="require('~/assets/img/pattern/ellipse-3.png')"
          class="hidden sm:block absolute bottom-24 right-20 w-6"
        />
        <img
          data-aos="fade-up"
          data-aos-delay="300"
          :src="require('~/assets/img/pattern/star.png')"
          class="hidden sm:block absolute top-20 sm:top-28 right-16 lg:right-0 lg:left-[32rem] w-8"
        />
      </BaseSection>
    </section>

    <!-- About Time Minder -->
    <section
      id="about"
      class="max-w-screen-xl mx-2 sm:mx-auto px-4 sm:px-6 lg:px-0 py-4 pb-20 sm:py-8 rounded-[2.25rem] sm:rounded-xl bg-white shadow-lg sm:shadow-md transform lg:-translate-y-12"
    >
      <div class="pl-12">
        <h2 class="text-4xl font-semibold">
          About <span class="text-time-gradient">Time </span> <span class="text-minder-gradient">Minder</span>
        </h2>
        <p data-aos="fade-up" class="paragraph text-center sm:text-left mr-10 mt-4 sm:mt-6">
          Time Minder adalah aplikasi yang didesain untuk membantu siapapun mengelola waktu mereka secara
          efisien guna meningkatkan produktivitas. Dengan antarmuka yang intuitif dan fitur yang dapat
          disesuaikan, Time Minder memungkinkan pengguna untuk mengatur sesi kerja dan istirahat sesuai
          dengan preferensi individu mereka.
        </p>
      </div>
    </section>

    <!-- Intoduction section -->
    <section class="w-full mt-36">
      <BaseSection data-aos="fade-down">
        <div class="col-span-12 lg:col-span-7">
          <div class="w-full">
            <img :src="require('assets/img/hero.png')" class="w-[70%]" alt="" />
          </div>
        </div>
        <div class="col-span-12 lg:col-span-5 space-y-6 px-4 sm:px-6 mt-20">
          <h2 class="text-4xl font-semibold">
            Introducing <span class="text-time-gradient">Time </span><span class="text-minder-gradient">Minder</span>
            Focus and Productivity Apps
          </h2>
          <p class="paragraph">Solusi terbaik mengatur waktu Anda secara efektif!</p>
          <ul class="space-y-4 sm:space-y-2">
            <LandingListItem title="Costumizable Timer" />
            <LandingListItem title="Intuitive Interface" />
            <LandingListItem title="Work-Break Ratio" />
          </ul>
        </div>
      </BaseSection>
    </section>

    <!-- Intro section -->
    <section id="features" class="bg-features relative max-w-full sm:mx-4 my-20 py-16 shadow rounded-2xl overflow-hidden">
      <div class="relative max-w-screen-xl px-4 sm:px-2 mx-auto grid grid-cols-12 gap-x-6">
        <HomepageImage class="sm:hidden" />
        <div data-aos="fade-right" class="col-span-12 lg:col-span-6 space-y-8 sm:space-y-6 px-4 sm:px-6 mt-8">
          <h2 class="text-4xl font-semibold">Our <span class="text-time-gradient">Features</span></h2>
          <div class="space-y-2">
            <h4 class="text-lg font-medium">Add Your Own Custom Timer</h4>
            <p class="paragraph text-sm xl:text-base">
              Kustomisasi waktu belajar dan istirahat secara fleksibel sesuai dengan preferensi masing-masing. Anda dapat menyesuaikan
              durasi belajar dan istirahat, serta menetapkan interval antara sesi belajar dan istirahat sesuai dengan kebutuhan Anda.
            </p>
          </div>
          <div class="space-y-2">
            <h4 class="text-lg font-medium">Focus Timer</h4>
            <p class="paragraph text-sm xl:text-base">
              Fitur-fitur utama kami dirancang untuk memberikan pengalaman pengguna yang lebih baik dalam mengelola
              waktu dan meningkatkan produktivitas.
            </p>
          </div>
          <div class="space-y-2">
            <h4 class="text-lg font-medium">List View Timer</h4>
            <p class="paragraph text-sm xl:text-base">
              Dengan tampilan list yang terstruktur, Anda dapat dengan mudah mengawasi waktu yang Anda habiskan pada
              setiap tugas dan mengelola jadwal Anda dengan lebih efisien.
            </p>
          </div>
        </div>
        <HomepageImage data-aos="fade-left" class="hidden sm:block" />
      </div>
    </section>

    <!-- Timer section -->
    <section class="w-full my-24">
      <div class="relative max-w-screen-xl justify-center items-center px-8 mx-auto grid grid-cols-12 gap-x-6">
        <div data-aos="fade-right" class="col-span-12 lg:col-span-6">
          <div class="w-full">
            <img :src="require('~/assets/img/timer.png')" class="w-70" alt="" />
          </div>
        </div>
        <div data-aos="fade-left" class="col-span-10 lg:col-span-5 space-y-8 sm:space-y-6 mt-8 xl:px-8">
          <h2 class="text-4xl font-semibold">Our Timer</h2>
          <ul class="space-y-8 sm:space-y-4">
            <LandingListItem title="Timer yang Dapat Disesuaikan">
              <p class="text-sm text-gray-700 leading-relaxed">
                Atur timer pribadi untuk sesi kerja dan istirahat, memungkinkan Anda menyesuaikan jadwal Anda
                sesuai dengan preferensi dan alur kerja Anda yang unik.
              </p>
            </LandingListItem>
            <LandingListItem title="Fokus dan Produktivitas">
              <p class="text-sm text-gray-700 leading-relaxed">
                Tetap fokus dan produktif sepanjang hari dengan antarmuka intuitif Time Minder dan fitur-fitur
                canggih yang dirancang untuk meningkatkan produktivitas Anda.
              </p>
            </LandingListItem>
            <LandingListItem title="Kompatibilitas Antar-Platform">
              <p class="text-sm text-gray-700 leading-relaxed">
                Akses Time Minder dengan lancar di berbagai perangkat dan platform, memastikan Anda tetap
                terorganisir dan berada dalam jalur yang benar di mana pun Anda berada.
              </p>
            </LandingListItem>
          </ul>
        </div>
      </div>
    </section>

    <!-- Getting started section -->
    <section class="bg-features relative max-w-full sm:mx-4 xl:mx-10 my-24 shadow sm:rounded-2xl overflow-hidden">
      <div class="w-full py-16 flex flex-col items-center">
        <h2 data-aos="flip-down" class="text-3xl sm:text-4xl font-semibold text-center">
          Ayo Coba <span class="text-time-gradient">Time </span>
          <span class="text-minder-gradient">Minder</span> Sekarang!
        </h2>
        <div
          data-aos="fade-up"
          class="relative w-full flex flex-col lg:flex-row items-center justify-between space-y-12 lg:space-y-0 px-4 xl:px-10 mt-16 sm:mt-8"
        >
          <LandingStep v-for="step in steps" :key="step.title" :step="step" />
          <img
            :src="require('~/assets/img/getting-started/arrow.png')"
            class="hidden lg:inline-block absolute top-32 left-64 xl:left-[22rem] w-24 xl:w-[9.5rem]"
            alt=""
          />
          <img
            :src="require('~/assets/img/getting-started/arrow.png')"
            class="hidden lg:inline-block absolute top-32 right-64 xl:right-[22rem] w-24 xl:w-[9.5rem]"
            alt=""
          />
        </div>
      </div>
    </section>

    <!-- FAQ section -->
    <section id="faq" class="w-full my-24">
      <BaseSection>
        <div data-aos="fade-right" data-aos-delay="150" class="col-span-12 lg:col-span-6">
          <div class="w-full">
            <img :src="require('~/assets/img/cat_hello.svg')" class="w-full" alt="" />
          </div>
        </div>
        <div data-aos="fade-left" data-aos-delay="150" class="col-span-12 lg:col-span-6 px-4 sm:px-6 mt-8">
          <span class="text-base text-gradient font-semibold uppercase mb-4 sm:mb-2">Support</span>
          <h2 class="text-3xl sm:text-4xl font-semibold mb-10 sm:mb-6">Frequently asked questions</h2>

          <ul class="shadow-box">
            <BaseAccordion v-for="(accordion, index) in accordions" :key="index" :accordion="accordion" />
          </ul>
        </div>
      </BaseSection>
    </section>

    <div class="w-full my-10 flex justify-center">
      <a
        v-smooth-scroll
        data-aos="flip-down"
        data-aos-delay="150"
        href="#hero"
        class="px-6 py-3 flex items-center space-x-2 bg-[#FAFAFA] hover:bg-gray-100 hover:shadow-md border border-[#DDDDDD] rounded-md text-gray-700"
      >
        <span>Back to top</span>
        <ArrowUpIcon :size="20" />
      </a>
    </div>
  </div>
</template>

<script>
import aosMixin from '@/mixins/aos'
import HomepageImage from "~/components/landing/HomepageImage.vue";
export default {
  name: 'IndexPage',
  components: {HomepageImage},
  mixins: [aosMixin],
  data() {
    return {
      selected: 0,
      dropdownConcurency: false,
      dropdownCrypto: false,
      accordions: [
        {
          title: 'Apa itu Time Minder?',
          description:
            "Time Minder adalah sebuah aplikasi timer yang dirancang khusus untuk membantu Anda meningkatkan fokus dan produktivitas Anda. Dengan fitur-fitur kustomisasi untuk istirahat, Time Minder membantu Anda mengatur waktu kerja dan istirahat Anda secara optimal, sehingga Anda dapat bekerja dengan lebih efisien.",
        },
        {
          title: 'Apa saja fitur utama yang ditawarkan oleh Time Minder?',
          description:
            "Time Minder menawarkan fitur utama berupa timer kustomisasi yang memungkinkan Anda mengatur periode kerja dan istirahat sesuai kebutuhan Anda. Anda dapat menyesuaikan durasi istirahat, mengatur interval antara periode kerja dan istirahat, serta menentukan jumlah siklus kerja-istirahat yang diinginkan.",
        },
        {
          title: 'Mengapa saya harus menggunakan Time Minder daripada aplikasi timer lainnya?',
          description:
            "Time Minder dirancang khusus untuk membantu Anda meningkatkan fokus dan produktivitas dengan pendekatan yang terbukti efektif. Dengan fitur-fitur kustomisasi untuk istirahat, Time Minder memungkinkan Anda mengatur pola kerja yang sesuai dengan ritme dan preferensi Anda, sehingga Anda dapat tetap fokus dan terorganisir sepanjang hari.",
        },
        {
          title: 'Bagaimana Time Minder dapat membantu saya secara konkret?',
          description:
            "Time Minder membantu meningkatkan produktivitas dengan memberikan kontrol yang lebih besar atas waktu kerja dan istirahat Anda. Dengan fitur yang memungkinkan pengaturan timer yang dapat digunakan kembali, Anda dapat mengatur pola kerja Anda sekali dan menggunakannya berkali-kali tanpa perlu menambahkannya lagi. Hal ini membantu Anda tetap fokus dan terorganisir, sehingga dapat mencapai hasil yang lebih baik dalam waktu yang lebih singkat.",
        },
      ],
      steps: [
        {
          img: 'cat_pencil.svg',
          title: 'Tambahkan Kegiatan dan Waktu',
          description:
            'Tambahkan kegiatan Anda dan atur waktu yang diperlukan untuk setiap kegiatan secara mudah dan cepat.',
        },
        {
          img: 'cat_setting.svg',
          title: 'Atur Kustom Waktu Jeda dan Jumlah Istirahat',
          description:
            'Atur waktu jeda antara sesi kerja dan istirahat Anda sesuai preferensi Anda, serta tentukan jumlah istirahat yang diinginkan.',
        },
        {
          img: 'cat_clock.svg',
          title: 'Gunakan Timer',
          description:
            'Mulai menggunakan timer untuk mengatur waktu kerja dan istirahat Anda dengan lebih teratur dan efisien.',
        },
      ],
    }
  },
}
</script>
<style scoped>
.text-time-gradient {
  background: rgb(255, 191, 28);
  background: linear-gradient(169.4deg, #ffbf1c -6.01%, #ffb700 36.87%, #f8f097 78.04%, #ffbf1c 103.77%);
  background-clip: text;
  -webkit-text-fill-color: transparent;
}

.text-minder-gradient {
  background: rgb(3, 10, 48);
  background: linear-gradient(169.4deg, #030A30 -6.01%, #030A30 36.87%, #94caff 78.04%, #030A30 103.77%);
  background-clip: text;
  -webkit-text-fill-color: transparent;
}

.bg-features {
  background: url('../assets/img/bg-section.webp');
  background-size: cover;
  background-position: center;
}
.max-h-0 {
  max-height: 0;
}
</style>
