<template lang="html">
  <div class="users_admin">
    <div class="users_admin-container">
      <div class="users_admin-header">
        <h1>Users</h1>
        <router-link to="/users/new" class="btn">Add New User</router-link>
      </div>
      <div class="users_admin-box">
        <table class="users_admin-table">
          <thead class="users_admin-bottom">
            <tr class="users_admin-descriptions">
              <th></th>
              <th>Avatar</th>
              <th>Name User</th>
              <th>Username</th>
              <th>Email</th>
              <th>Control</th>
            </tr>
          </thead>
          <tbody class="users_admin-list">
            <tr class="users_admin-user" v-for="item in 4">
              <td class="users_admin-checkbox">
                <input type="checkbox" />
              </td>
              <td class="users_admin-img">
                <img alt="Avatar of Zachary Gomez" class="avatar" src="https://placehold.co/40x40" />
              </td>
              <td class="users_admin-name">Zachary Gomez</td>
              <td class="users_admin-username">zachary-gomez</td>
              <td class="users_admin-email">zachary-gomez@gmail.com</td>
              <td class="users_admin-control">
                <router-link :to="`/users/${item}`"><i class="fas fa-edit"> </i></router-link>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>

</script>

<style scoped lang='scss'>
.users_admin {
  width: 100%;
  display: flex;
  justify-content: center;
  box-sizing: border-box;
  overflow-y: auto;
  background: #fff;
  padding: 3.2rem;

  @media(max-width: 1024px) {
    padding: 2rem;
  }

  &-container {
    width: 100%;
    border: #dadee6 0.1rem solid;
    border-radius: 0.8rem;
    background: #fff;
    box-shadow: 0 0 1rem rgba(0, 0, 0, 0.1);
    overflow: hidden;
  }

  &-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-bottom: 1px solid #e3e6f0;
    padding: 1rem 2rem;

    & h1 {
      font-size: 2rem;
      font-weight: 700;
    }

    & .btn {
      background-color: #4e73df;
      font-size: 1.2rem;
      color: #fff;
      padding: 1rem 2rem;
      border: none;
      border-radius: 0.5rem;
      cursor: pointer;

      &:hover {
        :hover {
          background-color: #2e59d9;
        }
      }
    }
  }

  &-box {
    overflow-x: auto;

    @media(max-width: 500px) {
      white-space: nowrap;
    }
  }

  &-table {
    width: 100%;
    border-collapse: collapse;

    & .users_admin {
      &-bottom {
        &>tr.users_admin-descriptions {
          padding: 1.5rem;
          text-align: left;
          border-bottom: 1px solid #e3e6f0;
          background-color: #fff;
          color: #858796;

          &>th {
            padding: 1.5rem;
            text-align: center;
            border-bottom: 1px solid #e3e6f0;
            background-color: #fff;
            color: #858796;
            font-size: 1.2rem;
            font-weight: 400;
          }
        }
      }

      &-list {
        &>tr.users_admin-user {
          & td {
            padding: 1.5rem;
            text-align: center;
            border-bottom: 1px solid #e3e6f0;
            color: #5a5c69;

            @media(max-width: 768px) {
              padding: .5rem;
              margin: 0 auto;
            }

            @media(max-width: 500px) {
              padding: 1.5rem;
            }
          }
        }
      }
    }
  }

  &-title {
    padding: 15px;
    text-align: left;
    border-bottom: 1px solid #e3e6f0;
  }

  &-control {

    & i {
      cursor: pointer;
      color: #858796;

      &:hover {
        color: #4e73df;
      }
    }
  }
}

.avatar {
  width: 5rem;
  height: 5rem;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;

  @media(max-width: 768px) {
    width: 4rem;
    height: 4rem;
    margin: auto;
  }
}

// @media (max-width: 1440px) {
//   .users_admin {
//     &-table {
//       & .users_admin {
//         &-list {
//           & > tr.users_admin-user {
//             & > td {
//               padding: 0.6rem 1rem;
//             }
//           }
//         }
//       }
//     }
//   }
// }
@media (max-width: 1280px) {
  .users_admin {
    &-table {
      & .users_admin {
        &-list {
          &>tr.users_admin-user {
            &>td {
              font-size: 1.3rem;
            }
          }
        }
      }
    }
  }
}

@media (max-width: 1024px) {
  .users_admin {
    &-header {
      padding: 1.5rem 2rem;

      & h1 {
        font-size: 1.8rem;
      }

      & .btn {
        padding: 0.8rem 1.5rem;
      }
    }

    &-table {
      & .users_admin {
        &-list {
          &>tr.users_admin-user {
            &>td {
              font-size: 1.2rem;
            }
          }
        }
      }
    }
  }
}

@media (max-width: 768px) {
  .users_admin {
    &-box {
      display: block;
    }

    &-table {
      & .users_admin {
        &-bottom {
          &>tr.users_admin-descriptions {
            padding: 1rem;

            &>th {
              padding: 1rem;
              font-size: 1.2rem;
            }
          }
        }
      }
    }
  }
}
</style>