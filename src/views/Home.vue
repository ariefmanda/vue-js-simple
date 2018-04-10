<template>
  <div id="page-container" class="sidebar-l sidebar-o side-scroll">
            <!-- Sidebar -->
            <nav id="sidebar">
                <!-- Sidebar Scroll Container -->
                <Sidebar/>
                <!-- END Sidebar Scroll Container -->
            </nav>
            <!-- END Sidebar -->
            <!-- Header -->
            <header id="header-navbar" class="content-mini content-mini-full">
                <!-- Header Navigation Right -->
                <Header/>
                <!-- END Header Navigation Left -->
            </header>
            <!-- END Header -->
            <!-- Main Container -->
            <main id="main-container" class="nice-copy">
              <Table/>
            </main>
    </div>
</template>

<script>
// @ is an alias to /src
import Sidebar from '../components/Sidebar'
import Header from '../components/Header'
import Table from '../components/Table'
export default {
  name: 'home',
  components:{
    Sidebar,
    Header,
    Table
  }
}
</script>
