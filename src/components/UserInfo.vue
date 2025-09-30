<script setup>
import UserInfoDescription from "./UserInfoDescription.vue";
import UserInfoContactLinks from "./UserInfoContactLinks.vue";
import avatar from "@/assets/avatar-01.JPG";
</script>

<template>
  <section class="user-info">
    <div class="user-info__base">
      <img class="user-info__avatar" :src="avatar" />
      <h2 class="user-info__name">香辛料</h2>
    </div>
    <UserInfoDescription></UserInfoDescription>
    <UserInfoContactLinks></UserInfoContactLinks>
  </section>
</template>

<style scoped>
.user-info {
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 10px;

  margin-right: 50px;
  margin-bottom: 40px;
}

.user-info__base {
  display: flex;
  flex-direction: row;
  align-items: center;
}

.user-info__avatar {
  width: 150px;
  aspect-ratio: 1;
  object-fit: cover;
  border-radius: 50%;

  transition: box-shadow 0.4s;
}

.user-info__avatar:hover {
  box-shadow: 0 0 20px rgba(255, 255, 255, 0.5);
}

.user-info__name {
  width: 120px;
  margin: 0;
  margin-left: 40px;
  text-align: center;

  font-size: 40px;
  color: rgba(56, 56, 56, 0.692);
  transition: color 0.3s ease;
}

.user-info__name:hover {
  color: rgb(255, 255, 255);
}

@media (max-width: 768px) {
  .user-info {
    margin-right: 0;
    margin-bottom: 30px;
    align-items: center;
  }
  .user-info__base {
    flex-direction: column;
    gap: 15px;
  }
  .user-info__avatar {
    width: 120px;
  }
  .user-info__name {
    margin-left: 0;
    font-size: 32px;
  }
}
</style>
