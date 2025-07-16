<template>
  <div class="q-pa-md" style="max-width: 400px">

    <q-form
      @submit="onSubmit"
      @reset="onReset"
      class="q-gutter-md"
    >
      <q-input
        filled
        v-model="name"
<<<<<<< HEAD
        label="Your name *"
        hint="Name and surname"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"
=======
        label="ชื่อ-สกุล *"
        hint="กรุณาใส่ชื่อและนามสกุล"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'ลองใหม่อีกรอบ']"
>>>>>>> thai-lang
      />

      <q-input
        filled
        type="number"
        v-model="age"
<<<<<<< HEAD
        label="อายุ: *"
        lazy-rules
        :rules="[
          val => val !== null && val !== '' || 'กรุณาพิมพ์อายุของคุณ',
          val => val > 0 && val < 100 || 'กรุณาใส่อายุที่ถูกต้องเถอะจ่ะ'
=======
        label="Your age *"
        lazy-rules
        :rules="[
          val => val !== null && val !== '' || 'Please type your age',
          val => val > 0 && val < 100 || 'Please type a real age'
>>>>>>> thai-lang
        ]"
      />

      <q-toggle v-model="accept" label="I accept the license and terms" />

      <div>
<<<<<<< HEAD
        <q-btn label="Submit" type="submit" color="primary"/>
        <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
=======
        <q-btn label="ยืนยัน" type="submit" color="primary"/>
        <q-btn label="ล้างc" type="reset" color="primary" flat class="q-ml-sm" />
>>>>>>> thai-lang
      </div>
    </q-form>

  </div>
</template>

<script>
import { useQuasar } from 'quasar'
import { ref } from 'vue'

export default {
  setup () {
    const $q = useQuasar()

    const name = ref(null)
    const age = ref(null)
    const accept = ref(false)

    return {
      name,
      age,
      accept,

      onSubmit () {
        if (accept.value !== true) {
          $q.notify({
            color: 'red-5',
            textColor: 'white',
            icon: 'warning',
            message: 'You need to accept the license and terms first'
          })
        }
        else {
          $q.notify({
            color: 'green-4',
            textColor: 'white',
            icon: 'cloud_done',
            message: 'Submitted'
          })
        }
      },

      onReset () {
        name.value = null
        age.value = null
        accept.value = false
      }
    }
  }
}
</script>
