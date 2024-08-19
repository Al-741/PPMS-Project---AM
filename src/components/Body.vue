<!-- BODY COMPONENTS -->

<!-------------------------------------->
<template>
  <div class="dashboard_container">
    <button @click="openPopup" class="manage_sections_btn">Manage Sections</button>
    <div class="grid_container">
      <section v-for="section in sectionsData" :key="section.title" class="dashboard_section">
        <h2>{{ section.title }}</h2>
        <div class="section_content">
          <div class="section_item" v-for="(label, index) in section.labels" :key="label">
            <div class="label">{{ label }}:</div>
            <div class="value">{{ section.values[index] }}</div>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<!-------------------------------------->
<script>
export default {
  name: 'BodyComponent',
  methods: {
    openPopup() {
      this.$emit('open_popup');
    },
  },
  props: {
    isDarkMode: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      sectionsData: [
        {
          title: 'My user profile',
          labels: ['Name', 'Email', 'Phone'],
          values: ['John Doe', 'johndoe@ppms.com', '+10000000000'],
        },
        {
          title: 'My training sessions',
          labels: [
            'Training session 1',
            'Training session 2',
            'Training session 3',
            'Training session 4',
            'Training session 5',
            'Training session 6',
          ],
          values: [
            'Pending approval',
            'Pending approval',
            'Pending approval',
            'Approved',
            'Approved',
            'Approved',
          ],
        },
        {
          title: 'My projects',
          labels: ['Project A', 'Project B', 'Project C', 'Project D'],
          values: ['Pending approval', 'Pending approval', 'Approved', 'Approved'],
        },
        {
          title: 'Orders',
          labels: ['Order 1', 'Order 2', 'Order 3'],
          values: ['Rejected', 'Approved', 'Approved'],
        },
        {
          title: 'My documents',
          labels: ['Document 1', 'Document 2', 'Document 3', 'Document 4'],
          values: ['Approved', 'Approved', 'Rejected', 'Approved'],
        },
        {
          title: 'Incidents',
          labels: ['Incident 1', 'Incident 2', 'Incident 3'],
          values: ['Pending', 'Pending', 'Pending'],
        },
        {
          title: 'Quotes',
          labels: ['Quote 1', 'Quote 2'],
          values: ['Pending approval', 'Pending approval'],
        },
      ],
    };
  },
};
</script>

<!-------------------------------------->
<style scoped>
.dashboard_container {
  background-color: var(--body-bg-color);
  padding: 20px;
  min-height: calc(100vh - 60px);
  box-sizing: border-box;
  transition: background-color 0.3s ease;
}

.grid_container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
}

.dashboard_section {
  background-color: var(--section-bg-color);
  border-radius: 12px;
  padding: 20px;
  transition: background-color 0.3s ease;
}

.dashboard_section h2 {
  margin-bottom: 10px;
  color: var(--title-color);
}

.section_content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 10px;
  padding: 10px;
  margin-top: 1rem;
  border-radius: 8px;
  transition: background-color 0.3s ease;
  background-color: var(--item-bg-color);
}

.section_item {
  display: flex;
  flex-direction: column;
  padding: 10px;
  transition: background-color 0.3s ease;
}

.section_item .label {
  font-weight: bold;
  color: var(--title-color);
}

.section_item .value {
  color: var(--paragraph-color);
  margin-top: 5px;
}

button{
  background-color: var(--body-bg-color);
  margin-bottom: 1rem;
  border-radius: 12px;
  padding-top: 16px;
  padding-bottom: 16px;
  padding-left: 32px;
  padding-right: 32px;
  border-color: var(--dark-link-color);
  color: var(--dark-link-color);
  

}

button:hover {
  background-color: var(--dark-link-color);
  color: var(--dark-title-color);
}


/* Dark Mode */
.dark_mode button{
  background-color: var( --footer-bg-color);
  color: var(--dark-paragraph-color)
}

.dark_mode button:hover{
  background-color: var(--dark-link-color);
  color: var(--dark-title-color);
}

.dark_mode .dashboard_container {
  background-color: var(--dark-body-bg-color);
}

.dark_mode .section_content {
  background-color: var(--dark-item-bg-color);
}

.dark_mode .dashboard_section {
  background-color: var(--dark-section-bg-color);
}

.dark_mode .dashboard_section h2 {
  color: var(--dark-title-color);
}

.dark_mode .section_item .label,
.dark_mode .section_item .value {
  color: var(--dark-paragraph-color);
}



/* Responsive */
@media (max-width: 768px) {
  .grid_container {
    grid-template-columns: 1fr;
  }
  
  .section_content {
    grid-template-columns: 1fr;
  }
  
  button{
  border-radius: 6px;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 16px;
  padding-right: 16px;
  

}

}
</style>
