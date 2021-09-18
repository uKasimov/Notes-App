<template>
  <div class="notes">
    <div class="note" :class="{ full: !grid }" v-for="(note, index) in notes" :key="index">
      <div class="note-header">
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
  &.full {
    width: 100%;
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
      margin: 0;
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