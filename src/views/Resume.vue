
<template>
  <div class="card">
      <Timeline :value="events" class="customized-timeline">
          <template #marker="slotProps">
              <span class="flex w-8 h-8 items-center justify-center text-white rounded-full z-10 shadow-sm" :style="{ backgroundColor: slotProps.item.color }">
              </span>
          </template>
        <!-- <template #opposite="slotProps">
            <h2 class="text-surface-500 dark:text-surface-400">{{ slotProps.item.year }}</h2>
        </template> -->
          <template #content="slotProps">
              <Card class="mt-4">
                  <template #title>
                      {{ slotProps.item.status }}
                  </template>
                  <template #subtitle>
                      {{ slotProps.item.date }}
                  </template>
                  <template #content>
                      <p>
                        {{ slotProps.item.content }}
                      </p>
                      <Button label="Read more" text></Button>
                  </template>
              </Card>
          </template>
      </Timeline>
  </div>
</template>

<script setup>
  import Timeline from 'primevue/timeline'
  import Card from 'primevue/card'
  import { ref } from "vue"

  const events = ref([
    { status: 'Full Stack Developer at timechange GmbH', year: '2022 - Present', color: '#FF9800', content: 'I co-develop three web applications for mananing pre and post event operations.'},
    { status: 'Frontend Developer at timechange GmbH', year: '2020 - 2022', color: '#FF9800', content: 'During my time at K3b GmbH as Software Developer, I have worked on several projects working on both Frontend and Backend.'},
    { status: 'Software Engineer at k3b GmbH', year: '2018 - 2020', color: '#FF9800' },
    { status: 'M.Sc Communication & IT at University of Bremen', year: '2014 - 2017', color: '#FF9800' },
    { status: 'B.Sc Telecommunication Engineering at NUCES FAST (Peshawar)', year: '2008 - 2012', color: '#FF9800' }
  ])

</script>

<style scoped lang="css">

  .p-timeline-event-content {
    flex: 1;
    flex-grow: 8;
  }

</style>
