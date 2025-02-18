<template>
    <section id="snippet-2" class="wrapper bg-light wrapper-border">
        <div class="container pt-15 pt-md-17 pb-13 pb-md-15">
            <div class="row gx-lg-8 gx-xl-12 gy-10 gy-lg-0">
                <div class="col-lg-4 mt-lg-2">
                    <h2 class="display-4 mb-3">Our Journal</h2>
                    <p class="lead fs-lg mb-6 pe-xxl-5">
                        Here are the latest news from our blog that got the most attention.
                    </p>
                    <a href="#" class="btn btn-soft-primary rounded-pill"
                    >View All News</a
                    >
                </div>
                <!-- /column -->
                <div class="col-lg-8">
                    <div
                        class="swiper-container blog grid-view mb-6"
                        data-margin="30"
                        data-dots="true"
                        data-items-md="2"
                        data-items-xs="1"
                    >
                        <Swiper
                            :space-between="30"
                            :pagination="{ el: '.pagi2', clickable: true }"
                            :modules="[Pagination]"
                            :breakpoints="{
                500: { slidesPerView: 1 },
                768: { slidesPerView: 2 },
                1024: { slidesPerView: 2 },
                1200: { slidesPerView: 2 },
              }"
                        >
                            <SwiperSlide v-for="(elm, i) in blogs1" :key="i">
                                <article>
                                    <figure class="overlay overlay-1 hover-scale rounded mb-5">
                                        <nuxt-link to="/about">
                                            <nuxt-img :src="elm.imageSrc" :alt="elm.imageAlt" />
                                            <span class="bg"></span>
                                        </nuxt-link>
                                        <figcaption>
                                            <h5 class="from-top mb-0">Read More</h5>
                                        </figcaption>
                                    </figure>
                                    <div class="post-header">
                                        <div class="post-category text-line">
                                            <a href="#" class="hover" rel="category">{{
                                                    elm.category
                                                }}</a>
                                        </div>
                                        <!-- /.post-category -->
                                        <h2 class="post-title h3 mt-1 mb-3">
                                            <nuxt-link class="link-dark" to="/about">{{
                                                    elm.postTitle
                                                }}</nuxt-link>
                                        </h2>
                                    </div>
                                    <!-- /.post-header -->
                                    <div class="post-footer">
                                        <ul class="post-meta mb-0">
                                            <li class="post-date">
                                                <i class="uil uil-calendar-alt"></i
                                                ><span>{{ elm.postDate }}</span>
                                            </li>
                                            <li class="post-comments">
                                                <a href="#"
                                                ><i class="uil uil-comment"></i>{{ elm.comments }}</a
                                                >
                                            </li>
                                        </ul>
                                        <!-- /.post-meta -->
                                    </div>
                                    <!-- /.post-footer -->
                                </article>
                            </SwiperSlide>
                        </Swiper>
                        <div class="swiper-controls">
                            <div
                                class="swiper-pagination swiper-pagination-clickable swiper-pagination-bullets swiper-pagination-horizontal pagi2"
                            ></div>
                        </div>
                        <!-- /.swiper -->
                    </div>
                    <!-- /.swiper-container -->
                </div>
                <!-- /column -->
            </div>
            <!-- /.row -->
        </div>
        <!-- /.container -->

        <!-- /.container -->
    </section>
</template>

<script setup>
import { blogs1 } from "~/data/blogs.js";
import { Swiper, SwiperSlide } from "swiper/vue";
import { Pagination } from "swiper/modules";
</script>

<style lang="scss" scoped></style>
