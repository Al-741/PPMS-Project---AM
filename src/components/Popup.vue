<!-- POPUP COMPONENTS -->

<!-------------------------------------->
<template>
  <div v-if="visible" class="popup_overlay">
    <div class="popup_content">

      <span class="close_cross" @click="closePopup">&times;</span>

      <h2>Manage Sections</h2>
      <p>Click to add or remove specific sections</p>
      <form>
        <div class="checkbox_container">
          <div class="checkbox_item" v-for="section in sections" :key="section.id">
            <input type="checkbox" :id="section.id" v-model="section.checked" class="custom_checkbox" />
            <label :for="section.id" class="custom_checkbox_label">
              <span class="custom_checkbox_icon">
                <span v-if="!section.checked">+</span>
                <span v-else>-</span>
              </span>
              {{ section.label }}
            </label>
          </div>
        </div>
      </form>
      <button @click="closePopup" class="validate_btn">Validate</button>
    </div>
  </div>
</template>


<!-------------------------------------->
<script>
export default {
  name: 'PopupComponent',
  props: {
    visible: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    closePopup() {
      this.$emit('close');
    },
  },
  data() {
    return {
      sections: [
        { id: 'profile', label: 'My user profile', checked: false },
        { id: 'training', label: 'My training sessions', checked: false },
        { id: 'projects', label: 'My projects', checked: false },
        { id: 'orders', label: 'Oders', checked: false },
        { id: 'documents', label: 'My documents', checked: false },
        { id: 'incidents', label: 'Incidents', checked: false },
        { id: 'qutoes', label: 'Quotes', checked: false },
      ],
    };
  },
};
</script>

<!-------------------------------------->
<style>
.popup_overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.7);
  display: flex;
  justify-content: center;
  align-items: center;
}

.popup_content {
  position: relative; 
  background: var(--bg-color);
  padding: 40px;
  border-radius: 16px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  text-align: center;
  max-width: 600px;
  width: 90%;
  color: var(--font-color);
  transition: background-color 0.3s ease, color 0.3s ease;
}

.popup_content h2 {
  margin-bottom: 20px;
  font-size: 24px;
  color: var(--font-color);
}

.popup_content p {
  margin-bottom: 30px;
  font-size: 16px;
  color: var(--font-color);
}


.close_cross {
  position: absolute;
  top: 10px; 
  right: 20px;
  font-size: 24px;
  cursor: pointer;
  color: var(--font-color);
  transition: color 0.3s ease;
}

.close_cross:hover {
  color: var(--link-hover-color);
}

.checkbox_container {
  display: grid;
  grid-template-columns: repeat(2, 1fr); 
  gap: 10px;
  margin-bottom: 20px;
}


.checkbox_item {
  display: flex;
  align-items: center;
}

.custom_checkbox {
  display: none;
}

.custom_checkbox_label {
  display: flex;
  align-items: center;
  cursor: pointer;
  font-size: 16px;
  color: var(--font-color);
}

.custom_checkbox_icon {
  width: 24px;
  height: 24px;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: var(--button-bg-color);
  color: var(--bg-color);
  font-weight: bold;
  margin-right: 10px;
  transition: background-color 0.3s ease, color 0.3s ease;
}

.custom_checkbox:checked + .custom_checkbox_label .custom_checkbox_icon {
  background-color: var(--link-hover-color);
  color: var(--bg-color);
}

.validate_btn {
  padding: 10px 20px;
  font-size: 16px;
  background-color: var(--button-bg-color);
  color: var(--bg-color);
  border-radius: 8px;
  border-color: var(--bg-color);
  cursor: pointer;
  transition: background-color 0.3s ease, color 0.3s ease;
}

.validate_btn:hover {
  border-style: line;
  border-color: var(--button-bg-color);
  background-color: var(--bg-color);
  color: var(--button-bg-color);
}


/* Dark Mode */
.dark_mode .popup_content {
  background-color: var(--dark-body-bg-color);
  color: var(--dark-title-color);
}

.dark_mode .validate_btn {
  border-color: var(--button-bg-color);
}

.dark_mode .validate_btn:hover {
  border-color: var(--button-bg-color);
  background-color: var(--dark-body-bg-color);
  color: var(--dark-title-color);
}



/* Responsive */
@media (max-width: 768px) {
  .popup_content {
    width: 60%;
    height: 50%;
    padding-bottom: 15px;
    padding-top: 5px; 
    border-radius: 16px;
    box-sizing: border-box;
  }

  .close_cross {
    top: 10px; 
    right: 20px; 
  }
}
</style>
