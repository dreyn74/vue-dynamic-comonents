<template>
  <div>
    <component v-for="(field, index) in schema" :key="index" :is="field.fieldType" v-bind="field"></component>
    <p>Hello {{formData.title}} {{formData.firstName}} {{formData.lastName}}, I hear you are {{formData.age}} years old.</p>
  </div>
</template>

<script>
import data from "./data.json";
import NumberInput from "../components/v4/NumberInput";
import SelectList from "../components/v4/SelectList";
import TextInput from "../components/v4/TextInput";
export default {
  name: "FormsDemo",
  components: { NumberInput, SelectList, TextInput },
  data() {
    return {
      formData: data,
      schema: [
        {
          fieldType: "SelectList",
          name: "title",
          multi: false,
          label: "Title",
          options: ["", "Mr", "Ms", "Honorable", "Dr", "Madam", "Lord"]
        },
        {
          fieldType: "TextInput",
          placeholder: "First Name",
          label: "First Name",
          name: "firstName"
        },
        {
          fieldType: "TextInput",
          placeholder: "Last Name",
          label: "Last Name",
          name: "lastName"
        },
        {
          fieldType: "NumberInput",
          placeholder: "Age",
          name: "age",
          label: "Age",
          minValue: 0
        }
      ],
      dataSchema: [
        {
          fieldType: "SelectList",
          name: "title",
          multi: false,
          label: "Title",
          options: ["", "Mr", "Ms", "Honorable", "Dr", "Madam", "Lord"]
        },
        {
          fieldType: "TextInput",
          placeholder: "First Name",
          label: "First Name",
          name: "firstName"
        },
        {
          fieldType: "TextInput",
          placeholder: "Last Name",
          label: "Last Name",
          name: "lastName"
        },
        {
          fieldType: "NumberInput",
          placeholder: "Age",
          name: "age",
          label: "Age",
          minValue: 0
        }
      ]
    };
  },
  computed: {
    fieldType: function() {
      return this.dataSchema;
    }
  }
};
</script>
