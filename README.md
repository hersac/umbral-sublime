# Soporte de Lenguaje Umbral para Sublime Text

Paquete oficial de Sublime Text para el lenguaje de programación **Umbral**. Proporciona resaltado de sintaxis completo y soporte para el desarrollo con archivos `.um`.

## ✨ Características

### 🎨 Resaltado de Sintaxis Completo

- **Comentarios**: Líneas que comienzan con `!!`
- **Strings**: Soporte para comillas simples, dobles y triple comillas
  - `'texto literal'` - String sin interpolación
  - `"texto con &variable"` - String con interpolación
  - `'''texto multilínea con &interpolacion'''`
- **Palabras Clave**: `i`, `e`, `wh`, `r`, `th`, `n`, `out`, `equip`, `origin`, `as`
- **Declaradores**: `v:`, `c:`, `f:`, `cs:`, `pr:`, `pu:`
- **Tipos de Datos**: `Int`, `Str`, `Flo`, `Bool`, `Void`, `[]`, `[][]`
- **Operadores**: `->`, `+`, `-`, `*`, `/`, `%`, `==`, `!=`, `<=`, `>=`, `<`, `>`, `&&`, `||`, `!`, `=`
- **Operador Spread**: `&array` para expandir arrays
- **Números y Booleanos**: `42`, `3.14`, `true`, `false`
- **Funciones Built-in**: `tprint`
- **Invocaciones**: Resaltado de llamadas a funciones y métodos

### 📦 Reconocimiento de Archivos

Automáticamente reconoce archivos con extensión `.um` como código Umbral.

## 🚀 Instalación

### Instalación Manual

1. Abre Sublime Text.
2. Ve al menú `Preferences` > `Browse Packages...`.
3. En la carpeta que se abre, abre una terminal y clona este repositorio:

```bash
git clone https://github.com/tu-usuario/umbral-sublime.git Umbral
```

4. Reinicia Sublime Text (opcional, generalmente detecta el cambio automáticamente).

## 📝 Ejemplo de Sintaxis

```umbral
!! Comentario de una línea

!! Declaración de variables y constantes
v: contador = 0;
c: PI = 3.14159;

!! Funciones
f: sumar(a->Int, b->Int)->Int {
    r: (a + b);
}

!! Condicionales
i: (contador > 0) {
    tprint("Contador positivo");
} e: {
    tprint("Contador cero o negativo");
}

!! Bucles
wh: (contador < 10) {
    tprint("Contador: &contador");
    contador = contador + 1;
}

!! Clases
cs: Persona {
    pr: nombre->Str;
    pr: edad->Int;
    
    pu f: Persona(nombre->Str, edad->Int) {
        th.nombre = nombre;
        th.edad = edad;
    }
    
    pu f: presentarse()->Void {
        tprint("Hola, soy &th.nombre");
    }
}

!! Instanciar y usar
c: persona = n: Persona("Juan", 25);
persona.presentarse();

!! Arrays y Operador Spread
c: numeros = {1, 2, 3};
c: masNumeros = {&numeros, 4, 5, 6};

!! Strings con interpolación
v: nombre = "Umbral";
tprint("Lenguaje: &nombre");
v: literal = 'Sin interpolación &nombre';
```

## 🎯 Características del Lenguaje Umbral

- **Variables**: `v:` (mutables) y `c:` (constantes)
- **Funciones**: `f:` con tipos explícitos y retornos
- **Clases**: `cs:` con propiedades (`pr:`) y métodos públicos (`pu:`)
- **Condicionales**: `i:` (if), `e:` (else)
- **Bucles**: `wh:` (while)
- **Arrays**: `{1, 2, 3}` con tipos `[]Int`, `[][]Int`
- **Interpolación**: `&variable` en strings y triple comillas
- **Operador Spread**: `&array` para expandir arrays
- **Módulos**: Sistema `equip`/`origin` para importar/exportar
- **Tipos Primitivos**: Int, Str, Flo, Bool, Void

## 📄 Licencia

Este proyecto está bajo la licencia especificada en el archivo LICENSE.

## 🤝 Contribuir

Las contribuciones son bienvenidas. Por favor:

1. Fork el repositorio
2. Crea una rama para tu feature (`git checkout -b feature/nueva-caracteristica`)
3. Commit tus cambios (`git commit -m 'Agrega nueva característica'`)
4. Push a la rama (`git push origin feature/nueva-caracteristica`)
5. Abre un Pull Request

## 📞 Soporte

- **Issues**: [GitHub Issues](https://github.com/tu-usuario/umbral-sublime/issues)
- **Documentación**: [Umbral Docs](https://umbral-lang.dev)

---

**Disfruta programando en Umbral! 🎉**
