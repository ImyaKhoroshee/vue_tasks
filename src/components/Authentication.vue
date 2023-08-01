<template>
  <p v-if="isAuth">Вы успешно вошли в систему</p>

  <form v-else>
    Логин <input type="text" /><br />
    Пароль <input type="text" /><br />
    <button>Войти</button>
  </form>
</template>

<script>
export default {
  props: { isAuth: Boolean },
  name: "Authentication",
};
</script>

<style scoped></style>

// Создайте компонент "Аутентификация" (Authentication), который будет отображать форму
входа или сообщение об успешной аутентификации в зависимости от переданного пропса
isAuthenticated. Используйте директиву v-if для условного отображения разных элементов в
шаблоне компонента.
