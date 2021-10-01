//1)Declara una clase Usuario
class Usuario {
  //2) Hacer que Usuario cuente con los siguientes atributos
  nombre = ``;
  apellido = ``;
  libros = new Array();
  mascotas = new Array();

  //Los valores de los atributos se deberán cargar a través del contructor, al momento de crear las instancias.
  constructor(nombre, apellido, libros, mascotas) {
    this.nombre = nombre;
    this.apellido = apellido;
    this.libros = libros;
    this.mascotas = mascotas;
  }

  //3) Hacer que Usuario cuente con los siguientes métodos:
  //3.1) getFullName(): String. Retorna el nombre completo del usuario. Utilizar template strings.
  getFullName() {
    return this.nombre + ` ` + this.apellido;
  }
  //3.2) addMascota(String): void. Recibe un nombre de mascota y lo agrega al array de mascotas.
  addMascota(nuevaMascota) {
    this.mascotas.push(nuevaMascota);
  }
  //3.3) countMascotas(): Number. Retorna la cantidad de mascotas que tiene el usuario.
  countMascotas() {
    return this.mascotas.length;
  }
  //3.4) addBook(String, String): void. Recibe un string 'nombre' y un string 'autor' y debe agregar un objeto: { nombre: String, autor: String} al array de libros.
  addBook(texto1, texto2) {
    let book = new Object();
    book["nombre"] = texto1;
    book["autor"] = texto2;
    this.libros.push(book);
  }
  //3.5) getBookNames(): String[]. Retorna un array con solo los nombres del array de libros del usuario.
  getBookNames() {
    let nombres = [];
    for (let i = 0; i < this.libros.length; i++) {
      nombres.push(this.libros[i].nombre);
    }
    return nombres;
  }
}

//4) Crear un objeto llamado usuario con valores arbitrarios e invocar todos sus métodos
const u = new Usuario(
  "Antonio",
  "Gallegos",
  [{ nombre: "El principito", autor: "Antoine de Saint-Exupéry" }],
  ["Perros", "Gatos", "Leones"]
);
console.log(u);
// Probamos metodo 3.1)
console.log(u.getFullName());
//Probamos metodo 3.2)
u.addMascota("Mono");
console.log(u.mascotas);
//Probamos metodo 3.3)
console.log(u.countMascotas());
//Probamos metodo 3.4)
u.addBook("El extranjero", "Albert Camus");
//Probamos metodo 3.5)
console.log(u.getBookNames());
