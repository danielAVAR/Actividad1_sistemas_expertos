

**1. ¿Cuál es la diferencia principal entre un sistema experto y un programa tradicional?**

Un programa tradicional tiene la lógica fija en el código. Un sistema experto separa las reglas del motor que las aplica, por lo que agregar un nuevo diagnóstico es simplemente agregar una regla, sin tocar el resto del programa.
 
---

**2. ¿Por qué se dice que el conocimiento está separado del motor? ¿Cuál es la ventaja?**

Las reglas (base de conocimiento) y el motor (funciones de inferencia) son independientes. La ventaja es que un experto puede agregar o cambiar reglas sin saber programar, y el mismo motor puede usarse para distintos dominios con solo cambiar las reglas.

---

**3. ¿Qué es la base de hechos y en qué se diferencia de la base de conocimiento?**

La base de hechos tiene los síntomas del caso actual (cambia con cada consulta). La base de conocimiento tiene las reglas generales que siempre aplican. Una es "lo que sé de este problema ahora", la otra es "lo que sé siempre".

---

**4. ¿Qué significa que un sistema experto pueda "explicar su razonamiento"? ¿Por qué importa en medicina o derecho?**

Significa que puede mostrar qué síntomas activaron qué regla. En medicina o derecho esto es crítico porque el profesional necesita validar la decisión antes de actuar. Una caja negra que solo da resultados no es aceptable cuando hay vidas o derechos en juego.

---

**5. ¿Por qué fracasaron los sistemas expertos en los años 90?**

1. Era muy difícil y caro capturar el conocimiento de los expertos en reglas.
2. Si aparecía un caso no previsto en las reglas, el sistema no sabía qué hacer.
3. Mantener las reglas actualizadas con el tiempo era insostenible.

---

**6. ¿Se activa la regla SI (fiebre AND tos) OR perdida_olfato con {fiebre=True, tos=False, perdida_olfato=True}?**

Sí. La evaluación es:

```
(True AND False) OR True
False OR True
True  ✓
```

Aunque no hay tos, la pérdida de olfato sola es suficiente para activar la regla.

---

**7. Tabla de verdad para (A AND NOT B) OR (NOT A AND B)**

| A | B | Resultado |
|---|---|-----------|
| F | F | F |
| F | V | V |
| V | F | V |
| V | V | F |

Es verdadera solo cuando A y B son distintos (equivale al XOR).

---

**8. ¿Diferencia entre encadenamiento hacia adelante y hacia atrás?**

**Hacia adelante:** Parte de los hechos y busca qué conclusión se puede sacar. Ejemplo: este sistema, donde el usuario da síntomas y el motor encuentra el diagnóstico.

**Hacia atrás:** Parte de una hipótesis y busca si los hechos la confirman. Ejemplo: un médico que sospecha de COVID y pide la prueba específica para confirmarlo.

---

**9. Tres reglas IF-THEN para recomendar lenguaje de programación**

```
SI objetivo = desarrollo_web     → aprender JavaScript
SI objetivo = analisis_de_datos  → aprender Python
SI objetivo = videojuegos        → aprender C#
```

---

**10. Red de inferencia**

```
desarrollo_web    → [R-A] → JavaScript
analisis_de_datos → [R-B] → Python
videojuegos       → [R-C] → C#
```

---

**11. ¿Qué pasa si dos reglas tienen las mismas condiciones pero distinta conclusión?**

Ambas se activarían siempre juntas y el sistema no sabría cuál aplicar. La solución más simple es asignarles distinto nivel de confianza para que la resolución de conflictos elija una. La solución correcta de fondo es revisar si faltan condiciones que las diferencien.
