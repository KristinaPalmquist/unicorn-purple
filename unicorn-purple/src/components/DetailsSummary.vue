<script setup>
import { ref } from 'vue';

const information = ref([
  { id: 1, name: 'John Doe' },
  { id: 2, name: 'Jane Doe' },
  { id: 3, name: 'John Smith' },
  { id: 4, name: 'Jane Smith' },
]);

const toggleExpanded = (info) => {
  info.expanded = !info.expanded;
};
</script>

<template>
  <div id="details-summary">
    <div v-for="info in information" :key="info.id" class="details-item">
      <details :open="info.expanded">
        <summary @click.prevent="toggleExpanded(info)" class="custom-summary">
          <div class="summary-content">
            Person {{ info.id }}
            <span :class="['toggle-summary', { expanded: info.expanded }]">
              <div class="toggle-text">
                {{ info.expanded ? 'Close' : 'Read more' }}
              </div>
              <div class="toggle-ball"></div>
            </span>
          </div>
        </summary>
        <p>
          {{ info.name }} says that their work means a lot to a lot of people.
        </p>
        <p>
          They are very proud of their work and they are very happy to be able
          to do it.
        </p>
      </details>
    </div>
  </div>
</template>

<style scoped>
#details-summary {
  margin: 0 auto;
  width: clamp(300px, 80%, 1200px);
  height: 50vh;
}
.details-item {
  width: 100%;
}
details summary {
  width: 100%;
  list-style: none;
  cursor: pointer;
  outline: none;
}

/* To hide default marker */
details summary::-webkit-details-marker {
  display: none;
}

.custom-summary {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px;
}

.summary-content {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 2rem;
}

.toggle-summary {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: var(--bg-color);
  width: 145px;
  padding: 0.5rem;
  border: 1px solid var(--primary-color);
  border-radius: 5px;
  position: relative;
  overflow: hidden;
}

.toggle-ball {
  width: 20px;
  height: 20px;
  background: linear-gradient(
    to bottom right,
    var(--secondary-color),
    var(--primary-color),
    var(--fourth-color)
  );
  border-radius: 50%;
  animation: ball-move-back 1s forwards;
}

.toggle-summary.expanded .toggle-ball {
  animation: ball-move 1s forwards;
}

.toggle-text {
  font-size: 0.8rem;
  animation: text-move-back 1s forwards;
}

.toggle-summary.expanded .toggle-text {
  animation: text-move 1s forwards;
}

@keyframes ball-move {
  0% {
    transform: translateX(0);
    background: linear-gradient(
      to bottom right,
      var(--secondary-color),
      var(--primary-color),
      var(--fourth-color),
      var(--fifth-color)
    );
  }
  33% {
    background: linear-gradient(
      to bottom right,
      var(--primary-color),
      var(--fourth-color),
      var(--fifth-color),
      var(--secondary-color)
    );
  }
  67% {
    background: linear-gradient(
      to bottom right,

      var(--fifth-color),
      var(--fourth-color),
      var(--primary-color),
      var(--secondary-color)
    );
  }
  100% {
    transform: translateX(-100px);
    background: linear-gradient(
      to bottom right,
      var(--fifth-color),
      var(--fourth-color),
      var(--primary-color),
      var(--secondary-color)
    );
  }
}

@keyframes ball-move-back {
  0% {
    transform: translateX(-100px);
    background: linear-gradient(
      to bottom right,
      var(--fifth-color),
      var(--fourth-color),
      var(--secondary-color)
    );
  }
  33% {
    background: linear-gradient(
      to bottom right,

      var(--fifth-color),
      var(--fourth-color),
      var(--primary-color),
      var(--secondary-color)
    );
  }
  67% {
    background: linear-gradient(
      to bottom right,
      var(--primary-color),
      var(--fourth-color),
      var(--fifth-color),
      var(--secondary-color)
    );
  }
  100% {
    transform: translateX(0);
    background: linear-gradient(
      to bottom right,
      var(--secondary-color),
      var(--primary-color),
      var(--fourth-color)
    );
  }
}

@keyframes text-move {
  0% {
    transform: translateX(0);
    opacity: 1;
  }
  25% {
    opacity: 0;
    transform: translateX(45px);
  }
  50% {
    opacity: 0;
  }

  75% {
    opacity: 0.4;
  }
  100% {
    transform: translateX(90px);
    opacity: 1;
  }
}

@keyframes text-move-back {
  0% {
    transform: translateX(90px);
    opacity: 1;
  }
  25% {
    opacity: 0.4;
  }
  50% {
    opacity: 0;
  }

  75% {
    opacity: 0;
    transform: translateX(45px);
  }
  100% {
    transform: translateX(0);
    opacity: 1;
  }
}
</style>
