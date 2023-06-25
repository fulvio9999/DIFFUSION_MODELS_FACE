# DIFFUSION_MODELS_FACE
Progetto Computer Vision su Diffusion Models per la generazione di volti

Per generare le 500 immagini, è possibile sia eseguire il notebook TEST.ipynb, oppure eseguire il comando "python main.py -test [path_output]"
Il notebook PROGETTO.ipynb sarebbe l'unione dei diversi sorgenti python.

### Per quanto riguarda i sorgenti python:
Il file principale da eseguire è: main.py

Due modalità: train e test.
* TRAIN: 	Per iniziare/continuare la fase di training
1. Eseguire il comando: python main.py -train
2. Verrà eseguita la fase di training continuando dall'ultima epoca (settings.NUM_EPOCH_FILE) e dall'ultimo checkpoint se presente (cartella settings.MODEL_PATH, nome del file settings.MODEL_FILE oppure settings.EMA_MODEL_FILE).
3. Nella cartella settings.MODEL_PATH verrà salvato il modello addestrato ad ogni fine epoca per aggiornare il checkpoint e nel file settings.NUM_EPOCH_FILE verrà aggiornato il numero di epoche in cui si è arrivati.
4. Nella cartella settings.RESULTS_PATH, verranno salvate ogni 10 epoche, il risultato di 12 immagini per il modello con e senza EMA.
5. L'addestramento verrà effettuato sulle immagini presenti nella cartella settings.DATASET_PATH e il file	di training è all'interno della stessa e si chiama settings.TRAIN_FILE.

* TEST:	Per generare le 500 immagini di output del task.
1. Eserguire il comando : python main.py -test [path_output]
2. [path_output] è il percorso dove verranno salvate le 500 immagini: è opzionale, se omesso verrà selezionato quello di default settings.OUTPUT_PATH.
3. Il file di test deve trovarsi nel percorso settings.TEST_FILE.
