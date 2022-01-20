
<template>
  <header>
    <div class="navbar">
      <NuxtLink to="/">
        <svg
          width="36"
          height="35"
          viewBox="0 0 36 35"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
          class="relative cursor-pointer z-[100]"
        >
          <g clip-path="url(#clip0_263_6)">
            <path
              d="M16.0364 33.9893C17.9566 35.1803 20.4119 34.4779 21.5211 32.4123L35.4613 6.47412C36.5705 4.41094 35.912 1.77241 33.9955 0.581411C32.0752 -0.610812 29.6199 0.0903517 28.5107 2.15598L14.5669 28.0954C13.4577 30.1598 14.1161 32.7983 16.0364 33.9893Z"
              fill="black"
            />
            <path
              d="M21.9168 29.7444L19.0669 33.9514L16.8352 34.1371L15.7859 25.8429L16.7338 24.0594L19.6118 18.7738L21.9168 29.7444Z"
              fill="black"
            />
            <path
              d="M19.966 34.0809C18.0458 35.2719 15.5917 34.5695 14.4813 32.5039L0.538665 6.5584C-0.570493 4.494 0.0879171 1.85548 2.00451 0.664474C3.92599 -0.526527 6.38007 0.175858 7.49045 2.24148L21.4343 28.1845C22.5447 30.2489 21.8875 32.8875 19.966 34.0809Z"
              fill="black"
            />
            <path
              d="M17.992 10.2279C20.8019 10.2279 23.0797 7.95007 23.0797 5.1402C23.0797 2.33034 20.8019 0.0524902 17.992 0.0524902C15.1821 0.0524902 12.9043 2.33034 12.9043 5.1402C12.9043 7.95007 15.1821 10.2279 17.992 10.2279Z"
              fill="black"
            />
          </g>
          <defs>
            <clipPath id="clip0_263_6">
              <rect width="36" height="34.6587" fill="white" />
            </clipPath>
          </defs>
        </svg>
      </NuxtLink>

      <div class="navs">
        <span class="pr-4 lg:hidden"
          >VersaBooks is an open, editable library catalog</span
        >
      </div>
    </div>
  </header>
</template>



<style lang="scss" scoped>
.navbar,
.navs {
  @apply flex items-center;
}
.navbar {
  @apply relative w-full max-w-[1440px] px-16 justify-start;

  @screen md {
    @apply px-6;
  }
}
.navs {
  @apply absolute inset-x-0 top-0 bottom-auto justify-center;
}
</style>