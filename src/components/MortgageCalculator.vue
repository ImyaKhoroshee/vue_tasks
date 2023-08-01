<template>
  <div>
    Введите сумму кредита <input v-model.number="credit" type="number" /><br />
    Введите процентную ставку <input v-model.number="percent" type="number" /><br />
    Введите срок кредита в месяцах <input v-model.number="period" type="number" /><br />
    <br />

    <h3>Ваш ежемесячный платеж составит - {{ calculate.paymentByMonth }} руб</h3>
    <h3>Общая сумма кредита составит - {{ calculate.totalPayment }} руб</h3>
  </div>
</template>

<script>
export default {
  props: { isAuth: Boolean },
  name: "MortgageCalculator",
  data() {
    return {
      credit: null,
      period: null,
      percent: null,
    };
  },
  computed: {
    calculate: function () {
      const principal = parseFloat(this.credit);
      const interestRate = parseFloat(this.percent) / 100 / 12;
      const loanTermMonths = parseFloat(this.period) * 12;

      const numerator =
        principal * interestRate * Math.pow(1 + interestRate, loanTermMonths);

      const denominator = Math.pow(1 + interestRate, loanTermMonths) - 1;

      const paymentByMonth = (numerator / denominator).toFixed(2);
      const totalPayment = (paymentByMonth * 12 * this.period).toFixed(2);
      return { paymentByMonth, totalPayment };
    },
    totalPayment: function () {},
  },
};
</script>

Создайте компонент MortgageCalculator с соответствующим шаблоном и скриптом. В шаблоне
компонента разместите поля ввода для суммы кредита, процентной ставки и срока кредита, а
также элементы для отображения ежемесячного платежа и общей суммы выплаты. Используйте
директиву v-model для связывания введенных пользователем значений с соответствующими
свойствами в компоненте. Создайте вычисляемое свойство monthlyPayment, которое будет
вычислять ежемесячный платеж на основе введенных значений суммы кредита, процентной ставки
и срока кредита. Создайте вычисляемое свойство totalPayment, которое будет вычислять общую
сумму выплаты по кредиту, учитывая ежемесячный платеж и срок кредита. Отобразите значения
monthlyPayment и totalPayment в соответствующих элементах шаблона. Вам необходимо создать
компонент ипотечного калькулятора, который позволяет пользователю вводить сумму кредита,
процентную ставку и срок кредита. Компонент должен автоматически вычислять ежемесячный
платеж и общую сумму выплаты по кредиту.
