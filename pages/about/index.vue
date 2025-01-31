<template lang="html">
  <div class="about_page">
    <div class="about_page-container">
      <div class="about_page-header">
        <h1>Pages > <span>About page</span></h1>
        <div class="about_page-buttons">
          <button class="about_page-button">Preview</button>
          <button class="btn">Add New User</button>
        </div>
      </div>
      <div class="about_page-content">
        <div class="page-main">
          <div class="page_container">
          <div class="page-save page-style">
            <h2 class="page-save-title">Name Page</h2>
            <button class="page-save-btn">Save Name</button>
          </div>
          <div class="page-description page-style">
            <div class="page-description-header">
              <h2 class="page-description-title">Preview Description</h2>
              <div class="page-buttons">
                <button class="page-button">x</button>
                <button class="page-button">x</button>
                <button class="page-button">x</button>
              </div>
            </div>
            <div class="page-type">
              <textarea
                name=""
                id=""
                cols="30"
                rows="10"
                class="page-textarea"
                placeholder="Type ..."
              ></textarea>
            </div>
          </div>
          <div class="page-gellery page-style">
            <div class="page-description-header">
              <h2 class="page-description-title">Gallery</h2>
              <div class="page-buttons">
                <button class="page-button">x</button>
                <button class="page-button">x</button>
                <button class="page-button">x</button>
              </div>
            </div>
            <div class="page-content">
              <div class="page-images">
                <div class="page-img" v-for="item in 2">
                  <button class="page-delete">x</button>
                  <img
                    alt="Profile photo of a person wearing a black turtleneck and an orange beanie"
                    src="https://placehold.co/375x240"
                  />
                </div>
              </div>
              <div class="page-addurl">
                <button class="page-add">Add Url</button>
              </div>
            </div>
          </div>
          <div class="page-quote page-style">
            <div class="page-description-header">
              <h2 class="page-description-title">Quote</h2>
              <div class="page-buttons">
                <button class="page-button">x</button>
                <button class="page-button">x</button>
                <button class="page-button">x</button>
              </div>
            </div>
            <div class="page-typetext">
              <textarea
                name=""
                id=""
                cols="30"
                rows="10"
                class="page-textarea"
                placeholder="Type ..."
              ></textarea>
            </div>
          </div>
          <div class="page-layout page-style">
            <div class="page-description-header">
              <h2 class="page-description-title">Photo Layout</h2>
              <div class="page-buttons">
                <button class="page-button">x</button>
                <button class="page-button">x</button>
                <button class="page-button">x</button>
              </div>
            </div>
            <div class="page-photo-layout">
              <div class="page-photo-content">
                <img
                    alt="Profile photo of a person wearing a black turtleneck and an orange beanie"
                    src="https://placehold.co/350x400"
                  />
              </div>
            </div>
          </div>
          </div>

          <div class="page_bottom">
            <div clas="page_bottom-header">
              <button class="page_bottom-button pgactive">Block</button>
              <button class="page_bottom-button">Widgets</button>
              <button class="page_bottom-button">Embeds</button>
            </div>
            <div class="page_bottom-blocks">
              <div class="page_bottom-block" v-for="item in 12">
                <p class='page_bottom-title'>Paragraph</p>
              </div>
            </div>
          </div>  
        </div>
        <div class="about_page-control">
          <div class="form-group">
            <label for="page-status">Status & Visibility</label>
            <select id="page-status">
              <option>Page Status: Published</option>
            </select>
          </div>
          <div class="form-group">
            <label for="url-address">URL Address</label>
            <select id="url-address">
              <option>About-page</option>
            </select>
          </div>
          <div class="form-group">
            <div class="toggle-switch">
              <input type="checkbox" id="page-visible" checked />
              <div class="slider"></div>
              <label for="page-visible">Page visible to systems</label>
            </div>
          </div>
          <div class="form-group">
            <label for="meta-tags">Meta Tags</label>
            <select id="meta-tags">
              <option>Tags</option>
            </select>
          </div>
          <div class="form-group">
            <label for="description">Description</label>
            <textarea id="description" rows="4" placeholder="Type..."></textarea>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<style scoped lang="scss">
.about_page {
  width: 100%;
  display: flex;
  justify-content: center;
  box-sizing: border-box;
  overflow-y: auto;
  background: #fff;
  padding: 3.2rem;
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
    padding: 2rem;
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
  &-content {
    display: flex;
  }
  &-button {
    padding: 1rem 2rem;
    border-radius: 0.8rem;
    border: 0.1rem solid #e0e0e0;
    background: transparent;
    color: #475166;
    margin-right: 1rem;
  }
  &-control {
    width: 25%;
    padding: 2rem;
  }
}
.page_container{
  width: 100%;
  max-width: 100%;
  padding: 2rem;
}
.page_bottom{
  padding: 2rem;
  &-header{
    display: flex;
    justify-content: center;
    margin-bottom: 2rem;
  }
  &-block{
    width: calc(100%/2 - 12px);
    height: 10%;
  }
  &-blocks{
    max-width: 100%;
    width: 100%;
    display: flex;
    align-items: flex-start;
    
  }
}
.page_bottom-header{
  display: flex;
  justify-content: center;
}
.page {
  &-main {
    width: 75%;
    border-right: 0.1rem solid #ccc;
    display: flex;
    flex-wrap: wrap;
    align-items: start;
    justify-content: start;
    row-gap: 2rem;
  }
  &-style {
    width: 100%;
    display: flex;
    flex-direction: column;
    border: 0.1rem solid #c8c8c8;
    border-radius: 0.8rem;
    background: #fcfcfc;
  }
  &-content {
    padding: 2rem;
  }
  &-images {
    display: flex;
    align-items: flex-start;
    column-gap: 1.2rem;
    row-gap: 0.6rem;
    justify-content: space-between;
    flex-wrap: wrap;

    & > * {
      max-width: calc(100% / 2 - 0.6rem);
      width: 100%;

      & img {
        width: 100%;
        max-width: 100%;
        height: 100%;
      }
    }
  }

  &-save {
    padding: 0.8rem 1.5rem;
    flex-direction: unset;
    justify-content: space-between;
    align-items: center;
    &-title {
      font-size: 1.6rem;
      font-weight: 700;
      color: #323b4d;
    }
    &-btn {
      border-radius: 0.8rem;
      font-size: 1.4rem;
      font-weight: 700;
      color: #475166;
      background: #fff;
      padding: 0.8rem 1.2rem;
      border: 0.1rem solid #b8b8b8;
    }
  }
  &-delete {
    position: absolute;
    top: 0;
    right: 0;
  }
  &-photo-layout {
    padding: 2rem;
  }
  &-photo-content {
    padding: 2rem;
    background: #f9fafc;
    border: 0.1rem solid #dadee6;
    border-radius: 0.8rem;
  }
  &-description {
    &-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 1.4rem 1.6rem;
      border-bottom: 1px solid #c8c8c8;
    }
    &-title {
      width: max-content;
      font-size: 1.6rem;
      color: #475166;
    }
  }
  &-buttons {
    display: flex;
    column-gap: 0.6rem;
  }
  &-button {
    border: 0.1rem solid #c8c8c8;
    border-radius: 50%;
    padding: 0.8rem 1.2rem;
  }
  &-textarea {
    width: 100%;
    height: 100%;
    resize: none;
    border: none;
    outline: none;
    overflow-y: auto;
    overflow-x: hidden;
    padding: 2rem;
    font-size: 1.6rem;
  }

  &-images {
    display: flex;
  }
}
.form-group {
  margin-bottom: 20px;
}
.form-group label {
  display: block;
  font-weight: bold;
  margin-bottom: 5px;
}
.form-group select,
.form-group textarea {
  width: 100%;
  padding: 10px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 14px;
}
.form-group .toggle-switch {
  display: flex;
  align-items: center;
}
.form-group .toggle-switch input {
  display: none;
}
.form-group .toggle-switch label {
  margin-left: 10px;
  font-size: 14px;
}
.form-group .toggle-switch .slider {
  position: relative;
  width: 40px;
  height: 20px;
  background-color: #ccc;
  border-radius: 20px;
  cursor: pointer;
  transition: background-color 0.3s;
}
.form-group .toggle-switch .slider:before {
  content: "";
  position: absolute;
  width: 18px;
  height: 18px;
  background-color: #fff;
  border-radius: 50%;
  top: 1px;
  left: 1px;
  transition: transform 0.3s;
}
.form-group .toggle-switch input:checked + .slider {
  background-color: #007bff;
}
.form-group .toggle-switch input:checked + .slider:before {
  transform: translateX(20px);
}
.page_bottom {
  width: 100%;
  border-top: 0.1rem solid #e0e0e0;
}
</style>