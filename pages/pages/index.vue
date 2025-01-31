Sanjar, [30.01.2025 12:16]
<template lang="html">
<div class="pages_list">
  <div class="pages-table-container">
    <div class="pages-table-header">
      <h1 class="table-header_title">Pages</h1>
      <button @click="addPage"><i class="fas fa-plus"></i><span class="table-btn">Add</span> New <span class="table-btn">Page</span></button>
    </div>
    <div class="table-container">
      <table>
        <thead>
          <tr>
            <th></th>
            <th>Page Name</th>
            <th>Url</th>
            <th class="created-column">Created</th>
            <th class="last-edit-column">Last edit</th>
            <th>Control</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(page, index) in pages" :key="index">
            <td><input type="checkbox"/></td>
            <td>{{ page.name }}</td>
            <td>{{ page.url }}</td>
            <td>{{ page.created }}</td>
            <td>{{ page.lastEdit }}</td>
            <td class="control-icons">
              <router-link :to="`/pages/${index}`"><i class="fas fa-edit"></i></router-link>
              <i class="fas fa-trash"></i>
              <i class="fas fa-eye"></i>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</div>
</template>

<script scoped>
export default {
  data() {
    return {
      pages: [
        {
          name: "Privacy Policy",
          url: "/privacy-policy/",
          created: "2078/11/15",
          lastEdit: "2078/11/16",
          author: "Alice Johnson",
          posts: 2,
        },
        {
          name: "Terms and Conditions",
          url: "/terms-conditions/",
          created: "2078/11/18",
          lastEdit: "2078/11/19",
          author: "Mark Smith",
          posts: 0,
        },
        {
          name: "Our Services",
          url: "/services/",
          created: "2078/11/20",
          lastEdit: "2078/11/21",
          author: "Emily Clark",
          posts: 10,
        },
        {
          name: "FAQ",
          url: "/faq/",
          created: "2078/11/22",
          lastEdit: "2078/11/23",
          author: "Michael Brown",
          posts: 15,
        },
        {
          name: "Events",
          url: "/events/",
          created: "2078/11/30",
          lastEdit: "2078/12/01",
          author: "Jessica Taylor",
          posts: 25,
        },
        {
          name: "Careers",
          url: "/careers/",
          created: "2078/12/03",
          lastEdit: "2078/12/04",
          author: "David Lee",
          posts: 6,
        },
        {
          name: "Gallery",
          url: "/gallery/",
          created: "2078/12/05",
          lastEdit: "2078/12/06",
          author: "Olivia Scott",
          posts: 50,
        },
        {
          name: "Shop",
          url: "/shop/",
          created: "2078/12/07",
          lastEdit: "2078/12/08",
          author: "Liam Perez",
          posts: 100,
        },
        {
          name: "Testimonials",
          url: "/testimonials/",
          created: "2078/12/09",
          lastEdit: "2078/12/10",
          author: "Isabella Walker",
          posts: 30,
        },
        {
          name: "News",
          url: "/news/",
          created: "2078/12/11",
          lastEdit: "2078/12/12",
          author: "Ethan Rodriguez",
          posts: 18,
        },
        {
          name: "Support",
          url: "/support/",
          created: "2078/12/13",
          lastEdit: "2078/12/14",
          author: "Ava Martinez",
          posts: 12,
        },
        {
          name: "Partners",
          url: "/partners/",
          created: "2078/12/15",
          lastEdit: "2078/12/16",
          author: "Lucas Gonzalez",
          posts: 7,
        },
        {
          name: "Contact Sales",
          url: "/contact-sales/",
          created: "2078/12/17",
          lastEdit: "2078/12/18",
          author: "Mia Anderson",
          posts: 0,
        },
        {
          name: "About Us",
          url: "/about-us/",
          created: "2078/12/19",
          lastEdit: "2078/12/20",
          author: "James Moore",
          posts: 10,
        },
        {
          name: "Legal",
          url: "/legal/",
          created: "2078/12/21",
          lastEdit: "2078/12/22",
          author: "Charlotte Harris",
          posts: 1,
        },
        {
          name: "Store",
          url: "/store/",
          created: "2078/12/23",
          lastEdit: "2078/12/24",
          author: "Benjamin Young",
          posts: 2,
        },
      ],
    };
  },
};
</script>
<style lang="scss" scoped>
.pages_list {
  width: 100%;
  display: flex;
  justify-content: center;
  box-sizing: border-box;
  overflow-y: auto;
  background: #fff;
  padding: 3.2rem;
}
.pages-table-container {
  max-width: 100%;
  width: 100%;
  border: #dadee6 0.1rem solid;
  border-radius: 0.8rem;
  background: #fff;
  box-shadow: 0 0 1rem rgba(0, 0, 0, 0.1);
  overflow: hidden;
}
.pages-table-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 0.1rem solid #ccc;
  padding: 2rem;
}

.pages-table-header h1 {
  font-size: 24px;
  color: #343a40;
}

.pages-table-header button {
  display: flex;
  align-items: center;
  gap: 1rem;
  background-color: #007bff;
  color: white;
  border: none;
  padding: 1rem 2rem;
  border-radius: 0.5rem;
  cursor: pointer;
}

table {
  width: 100%;
  border-collapse: collapse;
  background-color: white;
}

.table-container {
  overflow-x: auto;
}

th,
td {
  padding: 1.5rem;
  text-align: left;
  border-bottom: 1px solid #dee2e6;
}

th {
  background-color: #f8f9fc;
  color: #6c757d;
}

td {
  color: #343a40;
}

.control-icons i {
  margin-right: 1rem;
  cursor: pointer;
  color: #6c757d;
}

.control-icons i:hover {
  color: #007bff;
}

@media (max-width: 768px) {
  .table-container {
    display: block;
    white-space: nowrap;
  }
  .header h1 {
    font-size: 18px;
  }
  .header button {
    padding: 5px 10px;
  }
  th,
  td {
    padding: 10px;
  }
}
@media (max-width: 480px) {
  .pages-table-header h1{
    font-size: 1.5rem;
  }
  .table-btn{
    display: none;
  }
}
</style>