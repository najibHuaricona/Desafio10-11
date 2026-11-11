# Finanzas Inteligentes – Simulador de Gradientes Conjugados Precondicionado

Proyecto académico de Métodos Numéricos (UMSA), desarrollado como una página web interactiva en un único archivo HTML con CSS y JavaScript integrados.

## Descripción

El simulador estudia la asignación de recursos entre cuatro áreas de una empresa boliviana hipotética:

- x₁: Marketing
- x₂: Tecnología
- x₃: Operaciones
- x₄: Recursos humanos

Resuelve sistemas lineales simétricos y definidos positivos de la forma **Ax = b** y compara el método de Gradientes Conjugados (GC) con Gradientes Conjugados Precondicionado (GCP), utilizando Jacobi como precondicionador diagonal.

> Los coeficientes y términos independientes son datos sintéticos con fines académicos. No representan información financiera real.

## Escenarios incluidos

1. **Ideal:** matriz SPD bien condicionada y necesidades estables.
2. **Bajo estrés financiero:** conserva la matriz base y modifica el vector b para representar cambios en necesidades y costos.
3. **Mal condicionado:** matriz SPD con escalas diagonales muy diferentes; se analiza el efecto del precondicionador de Jacobi.

## Funcionalidades

- Edición de los coeficientes de A y del vector b.
- Selección del vector inicial, tolerancia, precondicionador y máximo de iteraciones.
- Validación de simetría y definición positiva mediante el criterio de Sylvester y Cholesky.
- Solución de referencia mediante factorización de Cholesky.
- Implementación de GC y GCP.
- Cálculo de errores absolutos, relativos y porcentuales por variable.
- Cálculo del residuo relativo y números de condición.
- Gráficos de convergencia y comparación de soluciones.
- Cuatro pruebas QA.
- Exportación de resultados a CSV.

## Cómo ejecutar

No se necesita instalar programas, dependencias ni servidor.

1. Descarga o clona este repositorio.
2. Abre `finanzas_inteligentes_gcp_final.html` con Google Chrome, Firefox o Edge.
3. Selecciona uno de los tres escenarios.
4. Modifica los datos si deseas experimentar.
5. Pulsa **Calcular y actualizar todo**.
6. En el módulo QA, pulsa **Ejecutar las cuatro pruebas QA**.

## Archivos

- `finanzas_inteligentes_gcp_final.html`: aplicación completa (HTML, CSS y JavaScript en un solo archivo).
- `README.md`: documentación del proyecto.

## Métodos numéricos

Para una matriz simétrica definida positiva:

- **Cholesky:** A = LLᵀ; resuelve Ly = b y luego Lᵀx = y.
- **GC:** utiliza rₖ = b − Axₖ y direcciones conjugadas.
- **GCP:** aplica el precondicionador M y resuelve Mzₖ = rₖ. Con Jacobi, M es la diagonal de A.

El criterio de parada usado es:

`||rₖ||₂ / ||b||₂ < 10⁻⁶`

El número máximo de iteraciones predeterminado es 500.

## Validaciones y pruebas QA

El módulo QA incluye:

1. Carga y validación de los tres escenarios.
2. Rechazo de una matriz no simétrica o no definida positiva.
3. Verificación de que una edición en el vector independiente modifica la solución.
4. Comparación de iteraciones entre GC y GCP en el escenario mal condicionado.

Las pruebas se ejecutan en el navegador desde la propia página. Se recomienda ejecutarlas nuevamente después de cualquier modificación del código.

## Limitaciones

- El caso financiero es un modelo académico simplificado; no es una herramienta de asesoramiento financiero.
- El sistema trabaja con cuatro variables en los escenarios predefinidos, aunque el editor está diseñado para matrices 4 × 4.
- La convergencia depende de que A sea simétrica definida positiva y de la tolerancia seleccionada.
- Los resultados numéricos pueden variar levemente por redondeo de punto flotante del navegador.

## Autor

**Najib Brayan Huaricona Laurel**  
Universidad Mayor de San Andrés – Carrera de Informática  
Mención académica: completar según corresponda.

## Bibliografía

- Suñagua S., P. (2020). *Método de Gradientes Conjugados Precondicionado*. Revista Boliviana de Matemática – UMSA, 04, 2–7.
- Golub, G. H., & Van Loan, C. F. (2013). *Matrix Computations* (4th ed.). Johns Hopkins University Press.
- Saad, Y. (2003). *Iterative Methods for Sparse Linear Systems* (2nd ed.). SIAM.
