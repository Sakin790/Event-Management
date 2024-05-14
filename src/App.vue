<template>
  <div class="m-0 p-0 w-screen h-screen box-border text-white bg-gray-800">

    <div class="nav w-full h-[59px] bg-white flex justify-between bg-top">
      <a href=""
        class="font-bold text-xl items-center flex p-2 text-black hover:border-b border-green-500 transition duration-200 ease-in-out">VueX</a>
      <div class="text-black flex font-[14px] p-3 gap-3 items-center">
        <a href="" class="hover:border-b border-green-500 transition duration-200 ease-in-out">Guide</a>
        <a href="" class="hover:border-b border-green-500 transition duration-200 ease-in-out">API Referance</a>
        <a href="" class="hover:border-b border-green-500 transition duration-200 ease-in-out">Release Note</a>
        <a href="" class="hover:border-b border-green-500 transition duration-200 ease-in-out">v4.x</a>

        <div class="language-section relative" @mouseleave="isDropdownOpen = false">
          <a href="" class="hover:border-b border-green-500 transition duration-200 ease-in-out">Language</a>
          <ul v-show="isDropdownOpen"
            class="dropdown absolute top-full left-0 bg-white shadow-md rounded overflow-hidden">
            <li><a href="#">English</a></li>
            <li><a href="#">Spanish</a></li>
            <li><a href="#">French</a></li>
          </ul>
        </div>
      </div>
    </div>

  </div>
</template>
