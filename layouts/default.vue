<template>
    <div>
        <nav
      class="
        navbar navbar-dark
        bg-primary
        fixed-top
        flex-md-nowrap
        p-0
        shadow
        d-flex
      "
    >
      <li class="nav-item text-nowrap">
        <nuxt-link to="/" class="text-white mr-5">Logout</nuxt-link>
      </li>
      <a href="#" class="navbar-brand col-sm-3 col-md-w mr-0 text-center pr-5"
        >پنل ادمین</a
      >
      <input
        type="text"
        class="form-control form-control-primary"
        placeholder="جستجو..."
      />
      <ul class="navbar-nav px-3"></ul>
    </nav>

    

    <div class="d-flex">
      <div class="container sidebar-box">
        <div class="row">
          <div class="col-md-2 bg-light d-none d-md-block dropdown-header sidebar">
            <ul class="nav flex-column sidebar-nav">
              <div class="right-sidebar">
                <li class="nav-item">
                  <nuxt-link to="/" class="nav-link active">
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      width="16"
                      height="16"
                      fill="currentColor"
                      class="bi bi-chevron-compact-left"
                      viewBox="0 0 16 16"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M9.224 1.553a.5.5 0 0 1 .223.67L6.56 8l2.888 5.776a.5.5 0 1 1-.894.448l-3-6a.5.5 0 0 1 0-.448l3-6a.5.5 0 0 1 .67-.223z"
                      />
                    </svg>
                    خانه
                  </nuxt-link>
                </li>
                <li class="nav-item">
                  <nuxt-link to="/me" class="nav-link">
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      width="16"
                      height="16"
                      fill="currentColor"
                      class="bi bi-chevron-compact-left"
                      viewBox="0 0 16 16"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M9.224 1.553a.5.5 0 0 1 .223.67L6.56 8l2.888 5.776a.5.5 0 1 1-.894.448l-3-6a.5.5 0 0 1 0-.448l3-6a.5.5 0 0 1 .67-.223z"
                      />
                    </svg>
                   مشاهده اطلاعات خود
                  </nuxt-link>
                </li>
                <li class="nav-item">
                  <nuxt-link to="/logout" class="nav-link">
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      width="16"
                      height="16"
                      fill="currentColor"
                      class="bi bi-chevron-compact-left"
                      viewBox="0 0 16 16"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M9.224 1.553a.5.5 0 0 1 .223.67L6.56 8l2.888 5.776a.5.5 0 1 1-.894.448l-3-6a.5.5 0 0 1 0-.448l3-6a.5.5 0 0 1 .67-.223z"
                      />
                    </svg>
                    خروج از محیط کاربری
                  </nuxt-link>
                </li>
<hr>
                <li class="nav-item">
                  <nuxt-link to="/admin" class="nav-link">
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      width="16"
                      height="16"
                      fill="currentColor"
                      class="bi bi-chevron-compact-left"
                      viewBox="0 0 16 16"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M9.224 1.553a.5.5 0 0 1 .223.67L6.56 8l2.888 5.776a.5.5 0 1 1-.894.448l-3-6a.5.5 0 0 1 0-.448l3-6a.5.5 0 0 1 .67-.223z"
                      />
                    </svg>
                    صفحه ادمین
                  </nuxt-link>
                </li>
            
<hr>
                <li class="nav-item">
                  <nuxt-link to="/expert" class="nav-link">
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      width="16"
                      height="16"
                      fill="currentColor"
                      class="bi bi-chevron-compact-left"
                      viewBox="0 0 16 16"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M9.224 1.553a.5.5 0 0 1 .223.67L6.56 8l2.888 5.776a.5.5 0 1 1-.894.448l-3-6a.5.5 0 0 1 0-.448l3-6a.5.5 0 0 1 .67-.223z"
                      />
                    </svg>
                    صفحه کارشناس
                  </nuxt-link>
                </li>
                
                
              </div>
            </ul>
          </div>
        </div>
      </div>
      <div class="container">
        <nuxt class="col-md-9 ml-sm-auto col-lg-10 px-auto pt-5 mt-5" />
      </div>
    </div>


    

    <!-- <div class="footer text-center bg-primary p-0">
      <br>
      <h1>footer</h1>
      <br>
      <br>
    </div> -->


    </div>
</template>

<script>
    export default {
        
    }
</script>

<style scoped>
* {
  direction: rtl;
  list-style: none;
}

.form-control-primary {
  margin: 10px;
  opacity: 0.9;
  border-radius: 2px;
}

.sidebar {
  /* position: fixed;  */
  top: 0; 
  right: 0;
  bottom: 0;
  z-index: 100;
  padding: 80px 0 0 50px;
  width: 200px;
  text-align: right;
}

.sidebar-right {
  position: sticky;
  top: 0;
  /* height: calc(100vh-70px); */
}


.sidebar-box{
  width: 30%;
  /* border-left: 1px solid #6c1515; */
}


.sidebar-nav li .nav-link {
  color: #333;
  font-weight: 500;
}

/* .navbar-brand{
  width: 20px !important;
} */
</style>
