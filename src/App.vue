<script setup>
import { ref, reactive } from 'vue'

const loginState = ref(false)
const count = ref(0)
const detail = reactive({
  name: "บรรจง พากเพียร",
  cash: 99
})

function addCash() {
  detail.cash += 50
}

const student ={
  name: "สมชาย ใจดี",
  department: "เทคโนโลยีสารสนเทศ",
  image: "https://placehold.co/200x200"
}
</script>


<template>
  <button @click="loginState = true">เข้าสู่ระบบ</button>
  <button @click="loginState = false">ออกจากระบบ</button>
  <p>{{ loginState }}</p>
  <p v-if="loginState==true">🥳 เข้าสู่ระบบแล้วนะ 🥳</p>
  <p v-else>🤗 ออกจากระบบแล้วนะ 🤗</p>

<div v-if="loginState==true">
  <p>ชื่อ : {{ detail.name }} มีเงิน {{ detail.cash }} บาท</p>
  <button @click="addCash">เพิ่มเงิน 50 บาท</button>

  <p>จำนวน : {{ count }}</p>
  <button @click="count++">เพิ่มจำนวน</button>
  <button @click="count--">ลดจำนวน</button>
  <h2>ข้อมูลนักเรียน</h2>
  <p>ชื่อ : {{ student.name }}</p>
  <p>สาขา : {{ student.department }}</p>
  <img :src="student.image">  
</div>
</template>