# Clase 10: Arquitectura de Computadores y S.O, y
Recuperación de Fallas

Claro, te puedo explicar sobre **undo logging** y **redo logging** en el contexto de bases de datos.

**Undo logging** es un método utilizado para garantizar la integridad de la base de datos en caso de que una transacción no se complete con éxito. Aquí está cómo funciona:

1. Antes de que una transacción modifique cualquier dato, se registra la versión original del dato en un log.
2. Si la transacción se completa con éxito, se realiza un **COMMIT** y los cambios se hacen permanentes.
3. Si la transacción falla o se interrumpe, el sistema utiliza el log para **deshacer** los cambios y restaurar los datos a su estado original.

Por otro lado, **redo logging** es utilizado para asegurar que las transacciones que han sido confirmadas con un **COMMIT** se mantengan incluso en caso de fallos del sistema. Funciona así:

1. La transacción realiza cambios en los datos y simultáneamente registra cada cambio en un log.
2. Si hay un fallo del sistema después de que la transacción ha hecho **COMMIT**, pero antes de que los cambios se hayan escrito completamente en el disco, el sistema puede usar el log para **rehacer** los cambios y asegurar que la base de datos refleje correctamente la transacción completada.

Ambos métodos son fundamentales para el concepto de **ACID** (Atomicidad, Consistencia, Aislamiento, Durabilidad) en las bases de datos, asegurando que las transacciones sean procesadas de manera segura y confiable. [El **undo logging** se ocupa de la atomicidad y la durabilidad, mientras que el **redo logging** ayuda con la durabilidad de las transacciones1](https://quizgecko.com/quiz/sistema-de-base-de-datos-registro-vntj4n).

Procedo a XD

Al final de lo que entendí, el undo logging se usa para volver al estado anterior en caso de fallo y el redo logging para volver a hacer la transaccion si el fallo ocurrió mientras se escribía en disco