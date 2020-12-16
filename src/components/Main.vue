<template>
  <div class="head">
    <nav class="navbar navbar-expand-md navbar-light sub-header">
      <div class="container">
        <ul class="navbar-nav mr-auto">
          <li class="nav-item active">
            <a class="nav-link" id="map" href="#">
              <svg xmlns="http://www.w3.org/2000/svg" width="15" height="15" fill="currentColor" class="bi bi-geo-alt-fill" viewBox="0 0 16 16">
                <path fill-rule="evenodd" d="M8 16s6-5.686 6-10A6 6 0 0 0 2 6c0 4.314 6 10 6 10zm0-7a3 3 0 1 0 0-6 3 3 0 0 0 0 6z"/>
              </svg>
              Волгоградасвая область <span class="sr-only">(current)</span></a>
          </li>
        </ul>
        
        <ul class="navbar-nav">
          <li class="nav-item">
              <a class="nav-link" href="#">Тендеры</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">База подрядчиков</a>
            </li>
          <li class="nav-item dropdown">
              <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                Другие сервисы
              </a>
              <div class="dropdown-menu" aria-labelledby="navbarDropdown">
                <a class="dropdown-item" href="#">Item1</a>
                <a class="dropdown-item" href="#">Item1</a>
                <a class="dropdown-item" href="#">Item3</a>
              </div>
            </li>
          </ul>
      </div>
    </nav>

    <nav class="navbar navbar-expand-lg navbar-light bg-white header">
      <div class="container">
        <a href="">
          <img src="../assets/logo-front.png" class="navbar-brand-img" alt="">
        </a>
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <div class="col-2">
              <div class="dropdown">
                <button class="btn btn-warning dropdown-toggle" type="button" id="dropdownMenu2" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                  <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="currentColor" class="bi bi-list" viewBox="0 0 16 16">
                    <path fill-rule="evenodd" d="M2.5 11.5A.5.5 0 0 1 3 11h10a.5.5 0 0 1 0 1H3a.5.5 0 0 1-.5-.5zm0-4A.5.5 0 0 1 3 7h10a.5.5 0 0 1 0 1H3a.5.5 0 0 1-.5-.5zm0-4A.5.5 0 0 1 3 3h10a.5.5 0 0 1 0 1H3a.5.5 0 0 1-.5-.5z"/>
                  </svg>
                  Каталог
                </button>
                <div class="dropdown-menu" aria-labelledby="dropdownMenu2">
                  <button class="dropdown-item" type="button">Item1</button>
                  <button class="dropdown-item" type="button">Item2</button>
                  <button class="dropdown-item" type="button">Item3</button>
                </div>
              </div>
          </div>
          <div class="col-7">
                <autocomplete 
                  id="Search"
                  :search="search"
                  placeholder="Хочу найти..."
                  aria-label="Хочу найти..."
                ></autocomplete>
          </div>
          <div class="col-2">
            <div class="dropdown">
                <button class="btn btn-light dropdown-toggle" type="button" id="dropdownMenu2" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                  Список
                </button>
                <div class="dropdown-menu" aria-labelledby="dropdownMenu2">
                  <button class="dropdown-item" type="button">Item1</button>
                  <button class="dropdown-item" type="button">Item2</button>
                  <button class="dropdown-item" type="button">Item3</button>
                </div>
              </div>
          </div>
          <div class="col-2">
            <button class='Circle'> A </button>
          </div>
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
const countries = [
  'Afghanistan',
  'Albania',
  'Algeria',
  'Andorra',
  'Angola',
  'Antigua & Barbuda',
  'Argentina',
  'Armenia',
  'Australia',
  'Austria',
  'Azerbaijan',
  'Bahamas',
  'Bahrain',
  'Bangladesh',
  'Barbados',
  'Belarus',
  'Belgium',
  'Belize',
  'Benin',
  'Bhutan',
  'Bolivia',
  'Bosnia & Herzegovina',
  'Botswana',
  'Brazil',
  'Brunei',
  'Bulgaria',
  'Burkina Faso'];

export default {
  name: "Main",
  props: {
    msg: String,
  },
  methods: {
    search(input) {
      if (input.length < 1) { return [] }
      return countries.filter(country => {
        return country.toLowerCase()
          .startsWith(input.toLowerCase())
      })
    }
  }
};
</script>

