El código descarga platos de categoría "Seafood".
Los guarda en una base de datos SQLite.
Te permite modificar el nombre de un plato.

Para comparar los tiempos que se tarda en iterar todos los elementos directamente desde la API con lo que se tarda en iterarlos desde la base de datos,
puede hacerse añadiendo este fragmento al código principal:
# Comparación de tiempos
    tiempo_api = medir_tiempo_api()
    tiempo_db = medir_tiempo_db()

    print(f"\n⏱️ Tiempo de iteración desde API: {tiempo_api:.5f} segundos")
    print(f"⏱️ Tiempo de iteración desde SQLite: {tiempo_db:.5f} segundos")
    if tiempo_db < tiempo_api:
        print("✅ Leer desde la base de datos fue más eficiente.")
    else:
        print("⚠️ Leer desde la API fue más rápido (probablemente por caché o pocos datos).")
