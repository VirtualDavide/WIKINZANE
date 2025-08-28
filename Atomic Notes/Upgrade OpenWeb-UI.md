2025-04-22 14:19

Tags : [[DailyLinux]]

# Upgrade OpenWeb-UI

**Istruzioni per l'Aggiornamento di Open-WebUI**

Queste istruzioni descrivono il processo di aggiornamento di Open-WebUI, presupponendo che tu l'abbia installato all'interno di un ambiente virtuale (venv) chiamato “openui-env” su un sistema Linux.

**Passaggi:**

1.  **Accedi alla Directory del Progetto:**
    
    ```
    cd <project directory>
    ```

2.  **Attiva l'Ambiente Virtuale:**

    ```
    source openui-env/bin/activate
    ```

3.  **Aggiorna Pip:**

    ```
    pip install --upgrade pip
    ```

4.  **Aggiorna Open-WebUI:**

    ```
    pip install --upgrade open-webui
    ```

5.  **Disattiva l'Ambiente Virtuale:**
    ```
    deactivate
    ```

**Note Importanti:**

*   **Ambiente Virtuale:** È *fondamentale* utilizzare un ambiente virtuale chiamato “openui-env” per isolare l'installazione di Open-WebUI da altre applicazioni sul tuo sistema.
*   **Verifica:** Dopo l'aggiornamento, verifica che la nuova versione di Open-WebUI sia in esecuzione correttamente.

## References

- 