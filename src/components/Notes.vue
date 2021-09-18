<template>
  <div class="notes">
    <div class="note" :class="{ full: !grid }" v-for="(note, index) in notes" :key="index">
<<<<<<< HEAD
      <div :class="{ full: !grid }" class="note-header">
=======
      <div class="note-header">
>>>>>>> origin/main
        <p>{{ note.title }}</p>
        <p style="cursor: pointer" @click="removeNote(index)">x</p>
      </div>
      <div class="note-body">
        <p>{{ note.descr }}</p>
        <span>{{ note.date }}</span>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    notes: {
      type: Array,
      required: true
    },
    grid: {
      type: Boolean,
      required: true
    }
  },
  methods: {
    removeNote(index) {
      console.log(`Note ${index} - removed`)
      this.$emit('remove', index)
    }
  }
}
</script>

<style lang="scss">
.notes {
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
  padding: 40px 0;
}

.note {
  width: 45%;
  padding: 18px 20px;
  margin:18px 20px;
  background-color: #ffffff;
<<<<<<< HEAD
  transition: all .25s cubic-bezier(.02,.01,.47,1);
  box-shadow: 0 30px 30px rgba(0,0,0,0.2);
  &:hover{
    box-shadow: 0 30px 30px rgba(0,0,0,.04);
    transform: translate(0, -6px);
    transition-delay: 0s !important;
  }
  &.full {
    width: 100%;
    text-align: center;
=======
  &.full {
    width: 100%;
>>>>>>> origin/main
  }
}

.note-header {
  display: flex;
  align-items: center;
  justify-content: space-between;

  h1 {
    font-size: 22px;
  }

  p {
    font-size: 22px;
    color: #402caf;
  }

  svg {
    cursor: pointer;
    color: #999999;
    margin-right: 12px;

    &.active {
      color: #402caf;
    }

    &:last-child {
<<<<<<< HEAD
      margin-right: 0;
    }
  }
  &.full {
     justify-content: center;
    p {
      margin-right: 16px;
      &:last-child{
        margin-right: 0;
      }
=======
      margin: 0;
>>>>>>> origin/main
    }
  }
}

.note-body {
  p {
    margin: 20px 0;
  }

  span {
    font-size: 14px;
    color: #999999;
  }
}
</style>