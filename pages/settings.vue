
<template>
  <div class="flex flex-col md:flex-row">
    <div class="mt-10 mx-10 mb-2 md:mx-15 md:sticky md:top-0">
      <div
        class="
          mb-3
          w-full
          flex flex-row flex-shrink
          md:flex-col
          justify-center
          items-center
          md:items-start
        "
      >
        <img
          class="
            z-0
            flex-shrink-0
            rounded-full
            md:rounded-lg
            w-16
            h-16
            object-cover
            md:mb-5
            md:h-64
            md:w-64
          "
          :src="profilePicture || ''"
        />
        <!-- <div
          class="
            z-10
            flex-shrink-0
            rounded-full
            md:rounded-lg
            w-16
            h-16
            md:mb-5
            md:h-64
            md:w-64
          "
        >
          Let's see
        </div> -->
        <div class="mx-3 md:mx-0">
          <div class="font-bold text-xl md:text-4xl">
            {{ this.username || "anonymous" }}
          </div>
          <div>{{ this.bio || "" }}</div>
          <div>{{ this.location || "" }}</div>
        </div>
      </div>
    </div>
    <div class="h-screen flex-grow flex flex-col mx-3 lg:mx-40">
      <div class="py-3 font-bold text-xl">User Settings</div>
      <input
        type="text"
        class="
          form-input
          my-3
          mt-1
          block
          w-full
          rounded-md
          bg-gray-100
          border-transparent
          focus:border-gray-500
          focus:bg-white
          focus:ring-0
        "
        placeholder="Artist Name"
        v-model="username"
      />
      <input
        type="text"
        class="
          form-input
          my-3
          mt-1
          block
          w-full
          rounded-md
          bg-gray-100
          border-transparent
          focus:border-gray-500
          focus:bg-white
          focus:ring-0
        "
        placeholder="Bio"
        v-model="bio"
      />
      <input
        type="text"
        class="
          form-input
          my-3
          mt-1
          block
          w-full
          rounded-md
          bg-gray-100
          border-transparent
          focus:border-gray-500
          focus:bg-white
          focus:ring-0
        "
        placeholder="Location"
        v-model="location"
      />
      <div class="flex justify-end md:justify-start">
        <button
          class="
            bg-purple-200
            hover:bg-purple-300
            text-purple-700 text-base
            font-semibold
            px-6
            py-2
            rounded-lg
          "
        >
          Save
        </button>
      </div>
      <div class="my-3"></div>
      <div class="py-3 font-bold text-xl">More Options</div>
      <hr />
      <div class="my-2 hover:font-bold">
        <a href="https://discord.gg/ZwpPGx98Qc">Join out Discord Community</a>
      </div>
      <hr />
      <div class="my-2 hover:font-bold">
        <a href="https://open.spotify.com/show/6LQi6uQ5nEgIK9vo0am9PS">In The Loop Podcast</a>
      </div>
      <hr />
      <div class="my-2 hover:font-bold">
        <a href="https://www.instagram.com/itl_studios/">Follow Us on Instagram</a>
      </div>
      <hr />
      <div class="my-2 hover:font-bold">
        <a href="https://intheloopstudio.com/privacy">Privacy Policy</a>
      </div>
      <hr />
      <div class="my-2 hover:font-bold">
        <a href="https://intheloopstudio.com/terms">Terms of Service</a>
      </div>
      <hr />
      <div class="my-2 hover:font-bold cursor-pointer">Sign Out</div>
      <hr />
      <div class="my-2">Download the App</div>
      <hr />
      <div class="text-red-400 my-2 cursor-pointer hover:font-bold">
        Delete Account
      </div>
    </div>
  </div>
</template>

<script>
export default {
  layout: "authenticated",
  async asyncData({ store }) {
    return {
      username: store.state.user.username ?? "anonymous",
      bio: store.state.user.bio ?? "",
      location: store.state.user.location ?? "",
      profilePicture: store.state.user.profilePicture ?? "",
    };
  },
};
</script>
