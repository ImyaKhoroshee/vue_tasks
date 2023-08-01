<template>
  <User :user="user" v-for="user in userList" :key="user.id" />
</template>

<script>
import User from "./User.vue";

export default {
  name: "UserList",
  components: { User },
  data() {
    return {
      userList: [
        { userName: "Вася", lastName: "Иванов", email: "tttt@mail.ru" },
        { userName: "Ира", lastName: "Боброва", email: "tttt@mail.ru" },
        { userName: "Петя", lastName: "Васильев", email: "tttt@mail.ru" },
      ],
    };
  },
};
</script>

<style scoped></style>

<!--   Создать компонент UserList, который будет отображать список пользователей из
переданного массива. Каждый пользователь должен быть представлен в виде отдельного
компонента User, принимающего пропсы с данными о пользователе (например, имя, фамилия, эл.
почта) -->
