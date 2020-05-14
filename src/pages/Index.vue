<template>
  <q-layout view="lHh lpr lFf">
    <q-header class="q-py-sm" style="background-color: #1c1b21;" :style="'border-bottom: 2px solid '+ theme_color">
        <q-toolbar>
        <span :style="'font-size: 35px;color:'+theme_color" class="my-font text-h6 q-mr-md">Kudos</span>
        <q-space ></q-space>
      <q-tabs v-model="selected_tab" shrink>
        <q-tab :style= "[selected_tab == 't_0' ? {backgroundColor: theme_color} : {}]" class="q-mr-sm q-py-xs custom_tab" @click="scrollToElement('id_portfolio');" style="width:120px;min-height:auto !important;color: white" label="Portfolio" />
        <q-tab :style= "[selected_tab == 't_1' ? {backgroundColor: theme_color} : {}]" class="q-mr-sm q-py-xs custom_tab" @click="scrollToElement('id_about_us');" style="width:120px;min-height:auto !important;color: white" label="About Us" />
        <q-tab :style= "[selected_tab == 't_2' ? {backgroundColor: theme_color} : {}]" class="q-mr-sm q-py-xs custom_tab" @click="scrollToElement('id_services');" style="width:120px;min-height:auto !important;color: white" label="Services" />
        <q-tab :style= "[selected_tab == 't_3' ? {backgroundColor: theme_color} : {}]" class="q-mr-sm q-py-xs custom_tab" @click="scrollToElement('id_testimonial');" style="min-height:auto !important;color: white" label="Testimonial" />
        <q-tab :style= "[selected_tab == 't_4' ? {backgroundColor: theme_color} : {}]" class="q-mr-sm q-py-xs custom_tab" @click="scrollToElement('id_team');" style="width:120px;min-height:auto !important;color: white" label="Team" />
        <q-tab :style= "[selected_tab == 't_5' ? {backgroundColor: theme_color} : {}]" class="q-mr-sm q-py-xs custom_tab" @click="scrollToElement('id_pricing');" style="width:120px;min-height:auto !important;color: white" label="Pricing" />
	<q-tab :style= "[selected_tab == 't_6' ? {backgroundColor: theme_color} : {}]" class="q-mr-sm q-py-xs custom_tab" @click="scrollToElement('id_news');" style="width:120px;min-height:auto !important;color: white" label="News" />
        <q-btn class="q-mr-md" size="12px" :style="'min-height:auto !important;background:'+ theme_color +'; color: white; padding:1px'" dense icon="color_lens">
            <q-tooltip transition-show="flip-right"
                       transition-hide="flip-left" self="center left" anchor="center right">Theme color
            </q-tooltip>
            <q-menu anchor="bottom left" self="bottom right" transition-show="flip-right"
                    transition-hide="flip-left">
              <q-color
                v-model="bg_color"
                no-header
                no-footer
                default-view="palette"
                class="my-picker"
                @input="changeBgColor()"
              />
            </q-menu>
          </q-btn>
          <a style="font-size: 25px;" class="float-right q-mr-sm" href="https://github.com/sponsors/mayank091193"
           target="_blank" title="Donate"><i class="fas fa-heart" style="color: #eb5daa"></i></a>
      </q-tabs>
        
      </q-toolbar>
    </q-header>
    <q-page-container>
      <q-page>
        <q-carousel
          animated
          v-model="slide"
          arrows
          swipeable
          navigation
          infinite
          autoplay
          control-color="white"
          transition-prev="slide-right"
          transition-next="slide-left"
          height="639px"
        >
          <q-carousel-slide class="q-pa-none" :name="1" img-src="/statics/images/image_1.jpg">
<div class="full-height full-width flex flex-center" style="background-color: rgba(0, 0, 0, 0.68) !important;">
            <div class="custom-caption">
              <div class="text-h2 main_line animation_2">WELCOME TO <span :style="'color:'+theme_color">KUDOS</span></div><br><br><br>
              <div class="text-h4 animation_1">The Web as I envisaged it, we have not seen it yet. The future<br> is still so much bigger than the past.</div><br><br><br>
<div class="animation_2">
<q-btn size="md" :style="'background:'+ theme_color +'; color: white'" label="READ MORE"/>
</div>
            </div>
</div>
          </q-carousel-slide>
          <q-carousel-slide class="q-pa-none":name="2" img-src="/statics/images/image_2.jpg">
<div class="full-height full-width flex flex-center" style="background-color: rgba(0, 0, 0, 0.68) !important;">
            <div class="custom-caption">
    	      <div class="text-h2 main_line animation_2" style="font-size:65px;"><span :style="'color:'+theme_color">KUDOS</span> FOR THE BEST</div><br><br><br>
              <div class="text-h4 animation_1">A man who dares to waste one hour of time has <br>not discovered the value of life.</div><br><br><br>
<div class="animation_2">
<q-btn size="md" :style="'background:'+ theme_color +'; color: white'" label="READ MORE"/>
</div>
            </div>
</div>
          </q-carousel-slide>
          <q-carousel-slide class="q-pa-none":name="3" img-src="/statics/images/image_3.jpg">
<div class="full-height full-width flex flex-center" style="background-color: rgba(0, 0, 0, 0.68) !important;">
            <div class="custom-caption">
    	      <div class="text-h2 main_line animation_2" style="font-size:65px;">THE PATH OF <span :style="'color:'+theme_color">SUCCESS</span></div><br><br><br>
              <div class="text-h4 animation_1">We have to stop optimizing for programmers and <br>start optimizing for users.</div><br><br><br>
<div class="animation_2">
<q-btn size="md" :style="'background:'+ theme_color +'; color: white'" label="READ MORE"/>
</div>
            </div>
</div>
          </q-carousel-slide>
        </q-carousel>
        <div class="row">
          <div class="col-md-3 col-lg-3 col-xs-12 col-sm-12">
            <q-card class="q-pa-sm flex flex-center text-center box-shadow" style="margin: 40px;">


              <q-card-section>
                <q-icon size="110px" name="ballot" :style="'color:'+theme_color"/>
                <div class="text-h6">Web &nbsp;Design</div>

              </q-card-section>

              <q-card-section class="q-pt-none">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
                eiusmod tempor incididunt.
              </q-card-section>
            </q-card>
          </div>
          <div class="col-md-3 col-lg-3 col-xs-12 col-sm-12">
            <q-card class="q-pa-sm flex flex-center text-center box-shadow" style="margin: 40px;">


              <q-card-section>
                <q-icon size="110px" name="view_comfy" :style="'color:'+theme_color"/>
                <div class="text-h6">Graphics Design</div>

              </q-card-section>

              <q-card-section class="q-pt-none">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
                eiusmod tempor incididunt.
              </q-card-section>
            </q-card>
          </div>
          <div class="col-md-3 col-lg-3 col-xs-12 col-sm-12">
            <q-card class="q-pa-sm flex flex-center text-center box-shadow" style="margin: 40px;">


              <q-card-section>
                <q-icon size="110px" name="people" :style="'color:'+theme_color"/>
                <div class="text-h6">Wordpress Theme</div>

              </q-card-section>

              <q-card-section class="q-pt-none">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
                eiusmod tempor incididunt.
              </q-card-section>
            </q-card>
          </div>

          <div class="col-md-3 col-lg-3 col-xs-12 col-sm-12">
            <q-card class="q-pa-sm flex flex-center text-center box-shadow" style="margin: 40px;">


              <q-card-section>
                <q-icon size="110px" name="people" :style="'color:'+theme_color"/>
                <div class="text-h6">Wordpress Plugin</div>

              </q-card-section>

              <q-card-section class="q-pt-none">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
                eiusmod tempor incididunt.
              </q-card-section>
            </q-card>
          </div>
        </div>
        <div class="quote">
          <div class="q-pt-xl full-width full-height flex flex-center" style="background-color: #000000ad !important;">
            <h3 class="text-white text-center">Lorem ipsum dolor sit amet, consectetur <br>adipiscing elit, sed do
              eiusmod tempor incididunt ut <br> labore et dolore magna aliqua.
              <br>
              <br>
              <q-btn type="a" href="https://github.com/sponsors/mayank091193" size="lg"
                     :style="'background:'+ theme_color +'; color: white'" label="Support Me"/>
            </h3>
          </div>
        </div>
        <div style="background: #f7f7f7" id="id_portfolio">
          <br>
          <div class="row">
            <div class="col-md-12 col-lg-12 col-xs-12 col-sm-12">
              <h5 class="text-center">Our Portfolio
                <br>
                <span class="text-center text-grey text-h6">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do.</span>
              </h5>
            </div>
          </div>
          <br>
          <div class="row text-center" style="padding-bottom: 99px">
            <div class="col-md-12 col-sm-12 col-xs-12 col-lg-12">
              <div style="line-height:0">
                <span v-for="index in 6" :key="index">
                  <q-flashcard :no-hover="hover" :style="style">
                    <q-flashcard-section transition="nudge-in" :active="active">
                      <img :src="'/statics/images/'+index+'.jpg'" width=340 height=263>
                    </q-flashcard-section>
                    <q-flashcard-section transition="fade-in" class="fit" :active="active">
                      <div class="fit" :style="background_style"></div>
                      <q-flashcard-section transition="drop-down" class="text-center my-header" :active="active">
                        Profile Title
                      </q-flashcard-section>
                      <q-flashcard-section transition="slide-up-in" class="my-text" :active="active">
                        For beautiful eyes, look for the good in others; for beautiful lips, speak only words of kindness; and for poise, walk with the knowledge that you are never alone.
                      </q-flashcard-section>
                      <q-flashcard-section transition="fade-in" class="fit flex justify-center items-end q-pb-lg"
                                           :active="active">
                        <q-btn class="q-mr-md" :style="'color:'+theme_color" style="background-color:white" round
                               icon="card_giftcard"/>
                        <q-btn :style="'color:'+theme_color" style="background-color:white" round icon="link"/>
                      </q-flashcard-section>
                    </q-flashcard-section>
                  </q-flashcard>
                  <br v-if="index==3"/>
                  </span>
              </div>
            </div>
          </div>
        </div>
        <div class="row" id="id_about_us">
          <div class="col-md-12 col-lg-12 col-xs-12 col-sm-12">
            <h5 class="text-center">About Us
              <br>
              <span
                class="text-center text-grey text-h6">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</span>
            </h5>
          </div>
        </div>
        <div class="row text-center flex flex-center">
          <div class="col-md-12 col-lg-12 col-sx-12 col-sm-12 q-gutter-md flex flex-center">
            <div class="col-md-4 col-lg-4 col-sx-12 col-sm-12">
              <q-card @mouseover="hoverOver(1)" @mouseout="hoverOutTimeout(1)" style="border: none;" class="my-card text-center box-shadow" flat bordered>
                <q-img
                  src="/statics/images/about_1.jpg"
                />

                <q-card-section>
                  <div class="text-overline text-orange-9">Overline</div>
                  <div :class="about_heading_1" :style="'color: ' + about_heading_color_1" class="about_heading_1 text-h6 q-mt-sm q-mb-xs">OFFICE PHILOSOPHY</div>
                  <div class="text-caption text-grey-9">
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                  </div>
                </q-card-section>
              </q-card>
            </div>
            <div class="col-md-4 col-lg-4 col-sx-12 col-sm-12">
              <q-card @mouseover="hoverOver(2)" @mouseout="hoverOutTimeout(2)" :style="'color: ' + about_heading_color_2" style="border: none;" class="my-card text-center box-shadow" flat bordered>
                <q-img
                  src="/statics/images/about_2.jpg"
                />

                <q-card-section>
                  <div class="text-overline text-orange-9">Overline</div>
                  <div :class="about_heading_2" :style="'color: ' + about_heading_color_2" class="text-h6 q-mt-sm q-mb-xs">OFFICE MISSION</div>
                  <div class="text-caption text-grey-9">
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                  </div>
                </q-card-section>
              </q-card>
            </div>
            <div class="col-md-4 col-lg-4 col-sx-12 col-sm-12">
              <q-card @mouseover="hoverOver(3)" @mouseout="hoverOutTimeout(3)" style="border: none;" class="my-card text-center box-shadow" flat bordered>
                <q-img
                  src="/statics/images/about_3.jpg"
                />

                <q-card-section>
                  <div class="text-overline text-orange-9">Overline</div>
                  <div :class="about_heading_3" :style="'color: ' + about_heading_color_3" class="text-h6 q-mt-sm q-mb-xs">OFFICE VALUE & RULES</div>
                  <div class="text-caption text-grey-9">
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore
                    et dolore magna aliqua.
                  </div>
                </q-card-section>
              </q-card>
            </div>
          </div>
        </div>
        <br>
        <br>
        <div style="background: #f7f7f7" id="id_services">
          <div class="row">
            <div class="col-md-12 col-lg-12 col-xs-12 col-sm-12">
              <h5 class="text-center">Our Services
                <br>
                <span
                  class="text-center text-grey text-h6">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</span>
              </h5>
            </div>
          </div> 
          <div class="q-pa-xl">       
            <div class="row q-col-gutter-sm ">
              <div class="col-md-4 col-lg-4 col-sm-12 col-xs-12">
                <q-item class="box-shadow q-pa-none q-ml-xs ">
                  <q-item-section side :style="'background-color:' + theme_color" class="q-pa-sm q-mr-none text-white">
                    <q-icon name="compare_arrows" size="65px"></q-icon>
                  </q-item-section>
                  <q-item-section class="q-pa-md q-ml-none">
                    <q-item-label class="text-h6 text-grey-9 text-uppercase">Blockchain</q-item-label>
                    <q-item-label class="text-grey-8">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</q-item-label>
                  </q-item-section>
                </q-item>
              </div>
              <div class="col-md-4 col-lg-4 col-sm-12 col-xs-12">
                <q-item class="box-shadow q-pa-none q-ml-xs">
                  <q-item-section side :style="'background-color:' + theme_color" class="q-pa-sm q-mr-none text-white">
                    <q-icon name="web" size="65px"></q-icon>
                  </q-item-section>
                  <q-item-section class="q-pa-md q-ml-none">
                    <q-item-label class="text-h6 text-grey-9 text-uppercase">Web Design</q-item-label>
                    <q-item-label class="text-grey-8">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</q-item-label>
                  </q-item-section>
                </q-item>
              </div>
              <div class="col-md-4 col-lg-4 col-sm-12 col-xs-12">
                <q-item class="box-shadow q-pa-none q-ml-xs q-mr-xs">
                  <q-item-section side :style="'background-color:' + theme_color" class="q-pa-sm q-mr-none text-white">
                    <q-icon name="fab fa-wordpress" size="65px"></q-icon>
                  </q-item-section>
                  <q-item-section class="q-pa-md q-ml-none">
                    <q-item-label class="text-h6 text-grey-9 text-uppercase">Wordpress</q-item-label>
                    <q-item-label class="text-grey-8">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</q-item-label>
                  </q-item-section>
                </q-item>
              </div>
            </div>
            <div class="row q-col-gutter-sm q-mt-lg">
              <div class="col-md-4 col-lg-4 col-sm-12 col-xs-12">
                <q-item class="box-shadow q-pa-none q-ml-xs ">
                  <q-item-section side :style="'background-color:' + theme_color" class="q-pa-sm q-mr-none text-white">
                    <q-icon name="settings" size="65px"></q-icon>
                  </q-item-section>
                  <q-item-section class="q-pa-md q-ml-none">
                    <q-item-label class="text-h6 text-grey-9 text-uppercase">DevOps</q-item-label>
                    <q-item-label class="text-grey-8">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</q-item-label>
                  </q-item-section>
                </q-item>
              </div>
              <div class="col-md-4 col-lg-4 col-sm-12 col-xs-12">
                <q-item class="box-shadow q-pa-none q-ml-xs">
                  <q-item-section side :style="'background-color:' + theme_color" class="q-pa-sm q-mr-none text-white">
                    <q-icon name="fas fa-database" size="65px"></q-icon>
                  </q-item-section>
                  <q-item-section class="q-pa-md q-ml-none">
                    <q-item-label class="text-h6 text-grey-9 text-uppercase">Big Data</q-item-label>
                    <q-item-label class="text-grey-8">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</q-item-label>
                  </q-item-section>
                </q-item>
              </div>
              <div class="col-md-4 col-lg-4 col-sm-12 col-xs-12">
                <q-item class="box-shadow q-pa-none q-ml-xs q-mr-xs">
                  <q-item-section side :style="'background-color:' + theme_color" class="q-pa-sm q-mr-none text-white">
                    <q-icon name="dynamic_feed" size="65px"></q-icon>
                  </q-item-section>
                  <q-item-section class="q-pa-md q-ml-none">
                    <q-item-label class="text-h6 text-grey-9 text-uppercase">AI</q-item-label>
                    <q-item-label class="text-grey-8">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</q-item-label>
                  </q-item-section>
                </q-item>
              </div>
            </div>
          </div>          
        </div>
<div class="quote" id="id_testimonial">
<div style="background-color: #000000ad !important;">
<q-carousel
      v-model="review_slide"
      swipeable
      animated
      infinite
      autoplay
      arrows
      navigation
      padding
      navigation-position="bottom"
      class="text-white full-height bg-transparent q-mx-xl"
    >
      <q-carousel-slide style="padding-bottom: 140px" name="style" class="column no-wrap flex-center">
        <img :style="'margin-top:100px;border-radius:5px;border: 4px solid ' + theme_color" src="/statics/images/team_1.jpg" width=150 height=150>
	<div class="q-mt-md text-h6 text-center">
	   <span :style="'color:'+theme_color">John Doe</span><br><span class="text-overline">Organization Founder</span>
	</div>
        <div class="q-mt-md text-h6 text-center">
          Lorem ipsum dolor sit amet, consectetur
adipiscing elit, sed do eiusmod tempor incididunt ut<br>
labore et dolore magna aliqua.
        </div>
      </q-carousel-slide>
      <q-carousel-slide style="padding-bottom: 140px" name="tv" class="column no-wrap flex-center">
        <img :style="'margin-top:100px;border-radius:5px;border: 4px solid ' + theme_color" src="/statics/images/team_2.jpg" width=150 height=150>
	<div class="q-mt-md text-h6 text-center">
	   <span :style="'color:'+theme_color">John Doe</span><br><span class="text-overline">Lead Developer</span>
	</div>
        <div class="q-mt-md text-h6 text-center">
          Lorem ipsum dolor sit amet, consectetur
adipiscing elit, sed do eiusmod tempor incididunt ut<br>
labore et dolore magna aliqua.
        </div>
      </q-carousel-slide>
      <q-carousel-slide style="padding-bottom: 140px" name="layers" class="column no-wrap flex-center">
        <img :style="'margin-top:100px;border-radius:5px;border: 4px solid ' + theme_color" src="/statics/images/team_3.jpg" width=150 height=150>
	<div class="q-mt-md text-h6 text-center">
	   <span :style="'color:'+theme_color">John Doe</span><br><span class="text-overline">Product Owner</span>
	</div>
        <div class="q-mt-md text-h6 text-center">
          Lorem ipsum dolor sit amet, consectetur
adipiscing elit, sed do eiusmod tempor incididunt ut<br>
labore et dolore magna aliqua.
        </div>
      </q-carousel-slide>
    </q-carousel>
</div>
</div>
        <div class="row" id="id_team">
            <div class="col-md-12 col-lg-12 col-xs-12 col-sm-12">
              <h5 class="text-center">Our Team
                <br>
                <span
                  class="text-center text-grey text-h6">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</span>
              </h5>
            </div>
          </div>        
          <div class="row text-center flex flex-center">
            <div class="col-md-12 col-lg-12 col-sx-12 col-sm-12 q-px-xl" style="width:100%;overflow:auto;">
              <q-carousel
              v-model="team_slide"
              transition-prev="slide-right"
              transition-next="slide-left"
              swipeable
              animated
	      infinite
              autoplay
              control-color="primary"
              navigation
              padding
              height="300px"
              class="rounded-borders"
            >
              <q-carousel-slide v-for="val in [1,2,3]" :key="val" :name="val" class="column no-wrap">
                <div class="row fit justify-center items-center q-gutter-xs q-col-gutter no-wrap">
                  <span v-for="index in 4" :key="index">
                  <q-flashcard :no-hover="hover" :style="team_style">
                    <q-flashcard-section transition="['nudge-out', 'fade-out']" :active="active">
                      <img :src="'/statics/images/team_'+index+'.jpg'" width=260 height=263>
                    </q-flashcard-section>
                    <q-flashcard-section transition="fade-in" class="fit" :active="active">
                      <div class="fit" :style="background_style"></div>
                      <q-flashcard-section transition="shake-down" class="text-center team-header" :active="active">
                        JOHN DOE
                      </q-flashcard-section>
                      <q-flashcard-section transition="spin-in" class="team-text" :active="active">
                        Founder and Director
                      </q-flashcard-section>
                      <q-flashcard-section style="padding-bottom: 50px" transition="slide-up-in" class="fit flex justify-center items-end"
                                           :active="active">
                        <q-btn class="q-mr-md" :style="'color:'+theme_color" style="background-color:white" round
                               icon="card_giftcard"/>
                        <q-btn :style="'color:'+theme_color" style="background-color:white" round icon="link"/>
                      </q-flashcard-section>
                    </q-flashcard-section>
                  </q-flashcard>
                  </span>
                </div>
              </q-carousel-slide>
            </q-carousel>
            </div>
          </div>          
          <div class="pricing" id="id_pricing">
          <div class="" style="background-color: #000000ad !important;">
          <div class="row">
            <div class="col-md-12 col-lg-12 col-xs-12 col-sm-12">
              <h5 class="text-center text-white">Our Pricing Plan
                <br>
                <span
                  class="text-center text-grey text-h6">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</span>
              </h5>
            </div>
          </div> 
          <div class="row q-col-gutter-sm q-px-xl">
          <div class="col-lg-3 col-md-3 col-xs-12 col-sm-6 q-px-lg">
            <q-card>
              <q-card-section class="text-white" style="background: #ec982f">
                <div class="text-h6 text-center">
                  FREE
                </div>
              </q-card-section>
              <q-card-section class="q-pa-md">
                <q-list dense padding style="border-bottom: 1px solid lightgrey;">
                  <q-item><span class="text-weight-bold">For small size companies</span></q-item>
                  <q-item>
                      50 GB storage
                  </q-item>
                  <q-item>
                      10 Domains
                  </q-item>
                  <q-item>
                      15 Projects
                  </q-item>
                  <q-item>
                      Free Deployment
                  </q-item>
                </q-list>
              </q-card-section>
              <q-card-section class="q-pa-none" style="color: #ec982f">
                <div class="text-center">
                  <span class="text-h2 text-center">$0</span>/mo
                </div>
              </q-card-section>
              <q-card-section>
                <div class="text-center q-px-lg">
                  <q-btn size="md" class="full-width q-pa-xs"
                     style="background: #ec982f; color: white" label="Choose Plan"/>
                     <br>
                     <div class="q-mt-md">Terms and Conditions apply</div>
                </div>
              </q-card-section>
            </q-card>
          </div>
          <div class="col-lg-3 col-md-3 col-xs-12 col-sm-6 q-px-lg">
            <q-card>
              <q-card-section class="text-white" style="background: #f4655f">
                <div class="text-h6 text-center">
                  STANDARD
                </div>
              </q-card-section>
              <q-card-section class="q-pa-md">
                <q-list dense padding style="border-bottom: 1px solid lightgrey;">
                  <q-item><span class="text-weight-bold">For medium companies</span></q-item>
                  <q-item>
                      50 GB storage
                  </q-item>
                  <q-item>
                      10 Domains
                  </q-item>
                  <q-item>
                      15 Projects
                  </q-item>
                  <q-item>
                      Free Deployment
                  </q-item>
                </q-list>
              </q-card-section>
              <q-card-section class="q-pa-none" style="color: #f4655f">
                <div class="text-center">
                  <span class="text-h2 text-center">$50</span>/mo
                </div>
              </q-card-section>
              <q-card-section>
                <div class="text-center q-px-lg">
                  <q-btn size="md" class="full-width q-pa-xs"
                     style="background: #f4655f; color: white" label="Choose Plan"/>
                     <br>
                     <div class="q-mt-md">Terms and Conditions apply</div>
                </div>
              </q-card-section>
            </q-card>
          </div>
          <div class="col-lg-3 col-md-3 col-xs-12 col-sm-6 q-px-lg">
            <q-card>
              <q-card-section class="text-white q-pa-md" style="background: #8b3bbd">
                <div class="text-h6 text-center">
                  PREMIUM
                </div>
              </q-card-section>
              <q-card-section class="q-pa-md">
                <q-list dense padding style="border-bottom: 1px solid lightgrey;">
                  <q-item><span class="text-weight-bold">For average companies</span></q-item>
                  <q-item>
                      50 GB storage
                  </q-item>
                  <q-item>
                      10 Domains
                  </q-item>
                  <q-item>
                      15 Projects
                  </q-item>
                  <q-item>
                      Free Deployment
                  </q-item>
                </q-list>
              </q-card-section>
              <q-card-section class="q-pa-none" style="color: #8b3bbd">
                <div class="text-center">
                  <span class="text-h2 text-center">$250</span>/mo
                </div>
              </q-card-section>
              <q-card-section>
                <div class="text-center q-px-lg">
                  <q-btn size="md" class="full-width q-pa-xs"
                     :style="'background: #8b3bbd; color: white'" label="Choose Plan"/>
                     <br>
                     <div class="q-mt-md">Terms and Conditions apply</div>
                </div>
              </q-card-section>
            </q-card>
          </div>
          <div class="col-lg-3 col-md-3 col-xs-12 col-sm-6 q-px-lg">
            <q-card>
              <q-card-section class="text-white" style="background: #3b97d1">
                <div class="text-h6 text-center">
                  PROFESSIONAL
                </div>
              </q-card-section>
              <q-card-section class="q-pa-md">
                <q-list dense padding style="border-bottom: 1px solid lightgrey;">
                  <q-item><span class="text-weight-bold">For large companies</span></q-item>
                  <q-item>
                      50 GB storage
                  </q-item>
                  <q-item>
                      10 Domains
                  </q-item>
                  <q-item>
                      15 Projects
                  </q-item>
                  <q-item>
                      Free Deployment
                  </q-item>
                </q-list>
              </q-card-section>
              <q-card-section class="q-pa-none" style="color: #3b97d1">
                <div class="text-center">
                  <span class="text-h2 text-center">$500</span>/mo
                </div>
              </q-card-section>
              <q-card-section>
                <div class="text-center q-px-lg">
                  <q-btn size="md" class="full-width q-pa-xs"
                     style="background:#3b97d1; color: white" label="Choose Plan"/>
                     <br>
                     <div class="q-mt-md">Terms and Conditions apply</div>
                </div>
              </q-card-section>
            </q-card>
          </div>
        </div>   
        <br>
        <br>
        </div></div>
<div class="row" id="id_news">
          <div class="col-md-12 col-lg-12 col-xs-12 col-sm-12">
            <h5 class="text-center">Latest News
              <br>
              <span
                class="text-center text-grey text-h6">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</span>
            </h5>
          </div>
        </div>
        <div class="row text-center flex flex-center">
          <div class="col-md-12 col-lg-12 col-sx-12 col-sm-12 q-gutter-md flex flex-center">
            <div class="col-md-4 col-lg-4 col-sx-12 col-sm-12">
              <q-card @mouseover="hoverOver(1)" @mouseout="hoverOutTimeout(1)" style="border: none;" class="my-card text-center box-shadow" flat bordered>
                <q-img
                  src="/statics/images/about_1.jpg"
                />

                <q-card-section class="text-left">

                  <div :class="about_heading_1" :style="'color: ' + about_heading_color_1" class="about_heading_1 text-h6 q-mt-sm q-mb-xs">LATEST NEWS 1</div>
                  <div class="text-caption text-grey-9 q-mt-sm">
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                  </div>
<div><br>
<q-btn size="sm" :style="'background:'+ theme_color +'; color: white'" label="READ MORE"/>
</div>
                </q-card-section>
              </q-card>
            </div>
            <div class="col-md-4 col-lg-4 col-sx-12 col-sm-12">
              <q-card @mouseover="hoverOver(2)" @mouseout="hoverOutTimeout(2)" :style="'color: ' + about_heading_color_2" style="border: none;" class="my-card text-center box-shadow" flat bordered>
                <q-img
                  src="/statics/images/about_2.jpg"
                />

                <q-card-section class="text-left">

                  <div :class="about_heading_2" :style="'color: ' + about_heading_color_2" class="text-h6 q-mt-sm q-mb-xs">LATEST NEWS 2</div>
                  <div class="text-caption text-grey-9 q-mt-sm">
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                  </div>
<div><br>
<q-btn size="sm" :style="'background:'+ theme_color +'; color: white'" label="READ MORE"/>
</div>
                </q-card-section>
              </q-card>
            </div>
            <div class="col-md-4 col-lg-4 col-sx-12 col-sm-12">
              <q-card @mouseover="hoverOver(3)" @mouseout="hoverOutTimeout(3)" style="border: none;" class="my-card text-center box-shadow" flat bordered>
                <q-img
                  src="/statics/images/about_3.jpg"
                />

                <q-card-section class="text-left">

                  <div :class="about_heading_3" :style="'color: ' + about_heading_color_3" class="text-h6 q-mt-sm q-mb-xs">LATEST NEWS 3</div>
                  <div class="text-caption text-grey-9 q-mt-sm">
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore
                    et dolore magna aliqua.
                  </div>
<div><br>
<q-btn size="sm" :style="'background:'+ theme_color +'; color: white'" label="READ MORE"/>
</div>
                </q-card-section>
              </q-card>
            </div>
          </div>
        </div>
        <br>
        <br>
<div class="contact_us" id="id_contact_us">
<div style="background-color: #000000ad !important;">
<div class="row" id="id_news">
  <div class="col-md-12 col-lg-12 col-xs-12 col-sm-12">
    <h5 class="text-center text-white">Contact Us
      <br>
      <span
        class="text-center text-grey text-h6">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</span>
    </h5>
  </div>
</div>
<div class="row text-center flex flex-center q-pb-lg">

<div class="col-md-6 col-lg-6 col-sx-12 col-sm-12 q-gutter-lg q-px-xl q-pb-none q-ma-none">
	      <q-input bg-color="white" outlined label="Your Name *">
		<template v-slot:append>
		  <q-icon name="event" :style="'color:' + theme_color" />
		</template>
	      </q-input>
<q-input bg-color="white" outlined label="Your Email *">
		<template v-slot:append>
		  <q-icon name="event" :style="'color:' + theme_color" />
		</template>
	      </q-input>
<q-input bg-color="white" outlined label="Your Phone *">
		<template v-slot:append>
		  <q-icon name="event" :style="'color:' + theme_color" />
		</template>
	      </q-input>
</div>
<div class="col-md-6 col-lg-6 col-sx-12 col-sm-12 q-gutter-lg q-px-xl q-pb-none q-ma-none">
<q-input class="" type="textarea" bg-color="white" outlined label="Your Message *">
<template v-slot:append>
		  <q-icon name="event" :style="'color:' + theme_color" />
		</template>
	      </q-input>
</div>
</div>
<div class="row flex flex-center text-center q-pb-xl q-mt-md">
<div class="col-md-12 col-lg-12 col-sx-12 col-sm-12">
<q-btn size="lg" :style="'background:'+ theme_color +'; color: white'" label="Send Message"/>
</div>
</div>
</div>
</div>
        <q-toolbar class="flex flex-center text-white" style="background-color: #1c1b21;" :style="'border-top: 2px solid '+ theme_color">
           <div class="q-pa-sm q-gutter-sm">
	    <q-btn round type="a" href="https://twitter.com/mayank91193"
                     :style="'background:'+ theme_color +'; color: white !important;'" icon="fab fa-twitter" />
	    <q-btn round type="a" href="https://github.com/mayank091193/vue-quasar-company-profile-website"
                     :style="'background:'+ theme_color +'; color: white !important;'" icon="fab fa-github" />
            <q-btn round type="a" href="mailto:mayank091193@gmail.com"
                     :style="'background:'+ theme_color +'; color: white !important;'" icon="email" />
	    <q-btn round type="a" href="https://github.com/sponsors/mayank091193"
                     :style="'background:'+ theme_color +'; color: white !important;'" glossy text-color="black" icon="fas fa-heart" />
	  </div>
        </q-toolbar>

      </q-page>
    </q-page-container>
  </q-layout>
</template>

<style src="@quasar/quasar-ui-qflashcard/dist/index.css"></style>

<script>
  import { scroll } from 'quasar'
  const { getScrollTarget, setScrollPosition } = scroll
    
    import {QFlashcard, QFlashcardSection} from '@quasar/quasar-ui-qflashcard'

    export default {
        components: {
            QFlashcard,
            QFlashcardSection
        },
        data() {
            return {
                slide: 1,
		            review_slide: 'style',
                selected_tab: 't_0',
                team_slide: 1,
                bg_color: 'rgb(0, 163, 82)',
                hover: false,
                active: false,
                theme_color: 'rgb(0, 163, 82)',
                background_style: 'background-color:rgba(0, 163, 82, 0.7);',
                about_heading_1: [],
                about_heading_2: [],
                about_heading_3: [],
                about_heading_color_1: '#424242',
                about_heading_color_2: '#424242',
                about_heading_color_3: '#424242'
            }
        },
        computed: {
            style() {
                return {
                    width: '340px',
                    height: '263px',
                    backgroundImage: `url('https://raw.githubusercontent.com/quasarframework/quasar-ui-qflashcard/dev/demo/src/statics/bgimg.jpg')`, // eslint-disable-line
                    textAlign: 'center',
                    boxShadow: '1px 1px 2px #e6e6e6',
                    display: 'inline-block'
                }
            },
            team_style() {
                return {
                    width: '260px',
                    height: '263px',
                    backgroundImage: `url('https://raw.githubusercontent.com/quasarframework/quasar-ui-qflashcard/dev/demo/src/statics/bgimg.jpg')`, // eslint-disable-line
                    textAlign: 'center',
                    boxShadow: '1px 1px 2px #e6e6e6',
                    display: 'inline-block'
                }
            }
        },
        methods: {
          scrollToElement (id) {
            let el = document.getElementById(id)
            const target = getScrollTarget(el)
            const offset = el.offsetTop + 3
            const duration = 900
            setScrollPosition(target, offset, duration)
          },
            changeBgColor() {
                this.theme_color = this.bg_color;
                this.background_style = 'background-color:' + this.bg_color.split(')')[0] + ',0.7)';
            },
            hoverOver: function(index) {
              this['about_heading_color_' + index] = this.theme_color;
              this['about_heading_' + index] = ['animated', 'bounceIn'];              
            },
            hoverOutTimeout: function(index) {
              this['about_heading_color_' + index] = '#424242';
              setTimeout(() => {
                this['about_heading_' + index] = [];                
              }, 1000);              
            },
        }
    }
</script>

<style lang="sass" scoped>
    .main_line
      font-size: 75px;
      letter-spacing: 5px;
      line-height: 60px;
      font-weight: 600;

    .custom-caption
      text-align: center;
      padding: 12px;
      color: white;

    .animation_1
      -webkit-animation: bounceIn 1s ease-in 800ms both;
      animation: bounceIn 1s ease-in 800ms both;

    .animation_2
      -webkit-animation: flipInX 2s ease-in-out 800ms both;
      animation: flipInX 1s ease-in-out 800ms both;

    .animation_3
      -webkit-animation: lightSpeedIn 1s ease-in 800ms both;
      animation: lightSpeedIn 1s ease-in 800ms both;

    .description
      padding: 10px
      background-color: black
      color: white
      box-shadow: 1px 1px 2px #e6e6e6

    .my-header
      width: 200px
      top: 0
      height: 45px
      color: black
      background-color: rgba(255,255,255, 0.8)
      text-transform: uppercase
      text-align: center
      font-size: 17px
      margin: 20px 0 0 68px
      padding: 25px

    .my-text
      width: 100%
      top: 0
      height: 90px
      color: white
      text-align: center
      font-size: 15px
      margin: 79px 0 0 0
      padding: 20px
      line-height: normal
      font-family: Georgia, serif
      font-style: italic

    .my-button-container
      width: 100%

    .my-button
      text-decoration: none
      text-transform: uppercase
      margin: 0 0 20px 0
      text-align: center
      padding: 7px 14px
      background-color: #000
      color: #fff
      text-transform: uppercase
      box-shadow: 0 0 1px #000
      transition-delay: 0.2s

    .my-button:hover
      box-shadow: 0 0 5px #000

    .box-shadow:hover
      box-shadow: 0 10px 13px -6px rgba(0, 0, 0, 0.2), 0 20px 31px 3px rgba(0, 0, 0, 0.14), 0 8px 38px 7px rgba(0, 0, 0, 0.12) !important;

    .my-card
      width: 350px
      max-width: 350px
      margin-top: 10px

    .team-header
      width: 100%
      top: 0
      height: 45px
      color: white
      text-transform: uppercase
      text-align: center
      font-size: 17px
      margin: 60px 0 0 0
      padding: 12px

    .team-text
      width: 100%
      top: 0
      height: 90px
      color: white
      text-align: center
      font-size: 15px
      margin: 100px 0 0 0
      padding: 20px
      line-height: normal
      font-family: Georgia, serif
      font-style: italic
    
    .quote
      background: url(/statics/images/parallax.jpg);
      background-size: cover;
      background-position: center;
      background-attachment: fixed;
      background-repeat: no-repeat;
    
    .pricing
      background: url(/statics/images/pricing.jpg);
      background-size: cover;
      background-position: center;
      background-attachment: fixed;
      background-repeat: no-repeat;
    
    .contact_us
      background: url(/statics/images/contact_us.jpg);
      background-size: cover;
      background-position: center;
      background-attachment: fixed;
      background-repeat: no-repeat;
    
    .custom_tab
      width: 130px;
</style>

