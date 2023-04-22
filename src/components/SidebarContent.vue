<template>
  <SidebarSection>
    <ul>
      <SidebarNavItem label="Home" icon="home" is-active />
      <SidebarNavItem label="Trending" icon="fire" />
      <SidebarNavItem label="Subscriptions" icon="collection" />
    </ul>
  </SidebarSection>
  <SidebarSection class="py-2 border-b">
    <ul>
      <SidebarNavItem label="Library" icon="duplicate" />
      <SidebarNavItem label="History" icon="clock" />
    </ul>
  </SidebarSection>
  <SidebarSection class="px-8 py-4 font-medium leading-5 border-b">
    <span class="text-sm">
      Sign in to like videos, comment, and subscribe.
    </span>
    <ButtonLogin
      class="focus:outline-none flex items-center px-2 py-0.5 mt-3 text-sm text-blue-700 uppercase border border-blue-700 rounded-sm"
    />
  </SidebarSection>
  <SidebarSection>
    <SidebarSectionHeading title="Best of YouTube" />
    <ul>
      <SidebarNavItem label="Music" icon="musicNote" />
      <SidebarNavItem label="Sports" icon="speakerphone" />
      <SidebarNavItem label="Gaming" icon="puzzle" />
      <SidebarNavItem label="Movies" icon="film" />
      <SidebarNavItem label="News" icon="newspaper" />
      <SidebarNavItem label="Live" icon="statusOnline" />
      <SidebarNavItem label="360&deg; Video" icon="eye" />
    </ul>
  </SidebarSection>

  <SidebarSection>
    <ul>
      <SidebarNavItem label="Browse channels" icon="plusCircle" />
    </ul>
  </SidebarSection>
  <SidebarSection>
    <SidebarSectionHeading title="More from YouTube" />
    <ul>
      <SidebarNavItem label="YouTube Premium" icon="play" />
      <SidebarNavItem label="Live" icon="statusOnline" />
    </ul>
  </SidebarSection>

  <SidebarSection>
    <ul>
      <SidebarNavItem label="Settings" icon="cog" />
      <SidebarNavItem label="Report History" icon="flag" />
      <SidebarNavItem label="Help" icon="questionMarkCircle" />
      <SidebarNavItem label="Send Feedback" icon="annotation" />
    </ul>
  </SidebarSection>

  <SidebarSection class="px-6 py-4 text-xs font-semibold space-y-4">
    <TheFooter />
    <!-- <section class="px-6 py-4 text-xs font-semibold space-y-4">
        <div>
          <a href="#" class="mr-2">About</a>
          <a href="#" class="mr-2">Press</a>
          <a href="#" class="mr-2">Copyright</a>
          <a href="#" class="mr-2">Contact us</a>
          <a href="#" class="mr-2">Creators</a>
          <a href="#" class="mr-2">Advertise</a>
          <a href="#" class="mr-2">Developers</a>
        </div>
        <div>
          <a href="#" class="mr-2">Terms</a>
          <a href="#" class="mr-2">Privacy</a>
          <a href="#" class="mr-2">Policy & Safety</a>
          <a href="#" class="mr-2">How YouTube works</a>
          <a href="#" class="mr-2">Test new features</a>
        </div>
        <div class="font-normal text-gray-500">&copy; 2021 Google LLC</div>
       </section> -->
  </SidebarSection>
</template>

<script lang="ts">
import SidebarSection from './SidebarSection.vue';
import SidebarSectionHeading from './SidebarSectionHeading.vue';
import SidebarNavItem from './SidebarNavItem.vue';
import ButtonLogin from './ButtonLogin.vue';
import TheFooter from './TheFooter.vue';
export default {
  components: {
    SidebarSection,
    SidebarSectionHeading,
    SidebarNavItem,
    ButtonLogin,
    TheFooter,
  },
};
</script>
