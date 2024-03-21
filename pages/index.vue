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
            Lorem Ipsum <span class="text-header-gradient">Dolor</span> Sit Amet
          </h1>
          <p data-aos="fade-down" data-aos-once="true" data-aos-delay="300" class="paragraph hidden sm:block">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit.
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
              Get Started
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
          class="hidden sm:block absolute bottom-56 right-24 w-6"
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
      class="max-w-screen-xl mx-2 sm:mx-auto px-4 sm:px-6 lg:px-0 py-4 pb-20 sm:py-8 rounded-[2.25rem] sm:rounded-xl bg-white shadow-lg sm:shadow-md transform lg:-translate-y-12"
    >
      <div class="pl-12">
        <h2 data-aos="fade-up" class="w-full flex text-4xl font-semibold text-center sm:text-left">
          About <span class="text-header-gradient"> Time Minder</span>
        </h2>
        <p data-aos="fade-up" class="paragraph text-center sm:text-left mr-10 mt-4 sm:mt-6">
          Time Minder is lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla nec purus feugiat, vestibulum
          lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla nec purus feugiat, vestibulum lorem ipsum dolor
          sit amet, consectetur adipiscing elit. Nulla nec purus feugiat, vestibulum
        </p>
      </div>
    </section>

    <!-- Intoduction section -->
    <section class="w-full mt-36">
      <BaseSection data-aos="fade-down">
        <div class="col-span-12 lg:col-span-7">
          <div class="w-full">
            <img :src="require('assets/img/imagedummy.webp')" class="w-[95%]" alt="" />
          </div>
        </div>
        <div class="col-span-12 lg:col-span-5 space-y-6 px-4 sm:px-6 mt-20">
          <h2 class="text-4xl font-semibold">
            Introducing the <span class="text-header-gradient">Time Minder</span> Focus and Productivity Apps
          </h2>
          <p class="paragraph">Lorem ipsum dolor sit amet </p>
          <ul class="space-y-4 sm:space-y-2">
            <LandingListItem title="Lorem ipsum dolor" />
            <LandingListItem title="Lorem ipsum dolor" />
            <LandingListItem title="Lorem ipsum dolor" />
          </ul>
        </div>
      </BaseSection>
    </section>

    <!-- Homepage section -->
    <section class="bg-features relative max-w-full sm:mx-4 my-20 py-16 shadow rounded-2xl overflow-hidden">
      <div class="relative max-w-screen-xl px-4 sm:px-2 mx-auto grid grid-cols-12 gap-x-6">
        <LandingHomepageImage class="sm:hidden" />
        <div data-aos="fade-right" class="col-span-12 lg:col-span-6 space-y-8 sm:space-y-6 px-4 sm:px-6 mt-8">
          <h2 class="text-4xl font-semibold">Lorem Ipsum <span class="text-header-gradient">Dolor</span></h2>
          <div class="space-y-2">
            <h4 class="text-lg font-medium">Lorem ipsum, Dolor sit amet</h4>
            <p class="paragraph text-sm xl:text-base">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla nec purus feugiat, vestibulum lorem ipsum
            </p>
          </div>
          <div class="space-y-2">
            <h4 class="text-lg font-medium">Lorem ipsum, Dolor sit amet</h4>
            <p class="paragraph text-sm xl:text-base">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla nec purus feugiat, vestibulum lorem ipsum
            </p>
          </div>
          <div class="space-y-2">
            <h4 class="text-lg font-medium">Lorem ipsum, Dolor sit amet</h4>
            <p class="paragraph text-sm xl:text-base">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla nec purus feugiat, vestibulum lorem ipsum
            </p>
          </div>
        </div>
        <LandingHomepageImage data-aos="fade-left" class="hidden sm:block" />
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
          <h2 class="text-4xl font-semibold">Lorem Ipsum</h2>
          <ul class="space-y-8 sm:space-y-4">
            <LandingListItem title="Lorem ipsum">
              <p class="text-sm text-gray-700 leading-relaxed">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla nec purus feugiat, vestibulum
                <span class="underline">Learn more</span> about our....
              </p>
            </LandingListItem>
            <LandingListItem title="Lorem ipsum">
              <p class="text-sm text-gray-700 leading-relaxed">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla nec purus feugiat, vestibulum
              </p>
            </LandingListItem>
            <LandingListItem title="Lorem ipsum">
              <p class="text-sm text-gray-700 leading-relaxed">
                Time Minder is <span class="underline">Lorem</span> and
                <span class="underline">Lorem ipsum</span> dolor sit amet, consectetur adipiscing elit. Nulla nec purus feugiat, vestibulum
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
          Ayo Coba Time Minder Sekarang
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
    <section class="w-full my-24">
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
        href="#navbar"
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
export default {
  name: 'IndexPage',
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
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla nec purus feugiat, vestibulum lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla nec purus feugiat, vestibulum',
        },
        {
          img: 'cat_setting.svg',
          title: 'Atur Kustom Waktu Jeda dan Jumlah Istirahat',
          description:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla nec purus feugiat, vestibulum lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla nec purus feugiat, vestibulum',
        },
        {
          img: 'cat_clock.svg',
          title: 'Gunakan Timer',
          description:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla nec purus feugiat, vestibulum lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla nec purus feugiat, vestibulum',
        },
      ],
    }
  },
}
</script>
<style scoped>
.text-header-gradient {
  background: rgb(255, 191, 28);
  background: linear-gradient(169.4deg, #ffbf1c -6.01%, #ffb700 36.87%, #f8f097 78.04%, #ffbf1c 103.77%);
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
