# vue-datatable
Vue2 dataTable fullOption custome language
## How to use
  ```
  <template>
    <datatable
          :data="data"
          :columns="columns"
          :actions="[]"
          :classMain="'main-table'"
          :classTable="'loss mt-20'"
          :language="language"
          :arrayPerPage="arrayPerPage"
          :defaultItemsPerPage="10"
        ></datatable>
  </template>
  <script>
  import Datatable from "@/components/DataTable";
  export default Vue.extend({
    components: { Datatable },
    data() {
    return {
      data: [
        {
          first_name: "Antonio",
          last_name: "Okoro",
          email: "cheezytony1@gmail.com",
          date_of_birth: "1998-05-15",
        },
        {
          first_name: "Naruto",
          last_name: "Uzumaki",
          email: "narutouzumaki@gmail.com",
          date_of_birth: "1987-10-10",
        },
        {
          first_name: "Sasuke",
          last_name: "Uchiha",
          email: "sasukeuchiha@gmail.com",
          date_of_birth: "1987-07-23",
        },
        {
          first_name: "Rock",
          last_name: "Lee",
          email: "rocklee@gmail.com",
          date_of_birth: "1985-11-27",
        },
        {
          first_name: "Neji",
          last_name: "Hyuga",
          email: "nejihyuga@gmail.com",
          date_of_birth: "1985-09-22",
        },
        {
          first_name: "Shikamaru",
          last_name: "Nara",
          email: "shikamarunara@gmail.com",
          date_of_birth: "1987-09-22",
        },
      ],
      columns: [
        { name: "first_name", th: "First Name" },
        { name: "last_name", th: "Last Name" },
        { name: "email", th: "Email Address" },
        { name: "phone", th: "Phone Number" },
        { name: "date_of_birth", th: "Date Of Birth", show: false },
        {
          name: "age",
          th: "Age",
          render(row) {
            // Parse date and display difference
            return moment(row.date_of_birth).fromNow();
          },
        },
      ],
      actions: [
        {
          text: "Delete",
          color: "danger",
          action: (row) => {
            alert(`about to delete ${row.first_name} ${row.last_name}`);
          },
        },
      ],
      language: {
        beforeTextPerpages: "",
        afterTextPerpages: "件表示",
        displayBeforeText: "",
        toText: "件中",
        searchText: "検索:",
        ofText: "から ",
        itemText: "まで表示",
        prevText: "前",
        nextText: "次",
      },
      arrayPerPage: [5, 10, 15, 25],
    };
  },
  ...
  })
  </script>
  ...
  ```
