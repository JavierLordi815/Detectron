 # Notas sobre la utilización de Detectron
 
 ## Llamadas útiles
 
 - La llamada más simple que se encuentra disponible en el tutorial inicial:
 
 ```
 python2 tools/infer_simple_png.py \
     --cfg configs/12_2017_baselines/e2e_mask_rcnn_R-101-FPN_2x.yaml \
     --output-dir /home/titan/data4Tb/videos/output \
     --image-ext png \
     --wts https://s3-us-west-2.amazonaws.com/detectron/35861858/12_2017_baselines/e2e_mask_rcnn_R-101-FPN_2x.yaml.02_32_51.SgT4y1cO/output/train/coco_2014_train:coco_2014_valminusminival/generalized_rcnn/        model_final.pkl \
     /home/titan/Desktop/frames/test_detectron
 ```
| Parámetro 	| Explicación breve 	|
|-------------------------------------------	|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|
| tools/infer_simple_png.py 	| Script de python (2.7.x) modificado para que la salida cualitativa sea en PNG en vez de PDF 	|
| cfg 	| Fichero de configuración del modelo elegido. e2e significa modelo End-to-end y son los más sencillos de utilizar al lanzar internamente tanto segmentación como clasificación de objetos localizada. 	|
| output-dir 	| Directorio para guardar las imágenes generadas a la salida 	|
| image-ext 	| Extensión de imagen en la carpeta de entrada que se quieren procesar 	|
| wts 	| Ruta al fichero de pesos. Si es una URL, comprueba primero si no está descargada y después la descarga. Tener cuidado con ésto, porque por defecto las guarda y busca en la carpeta /tmp/detectron... 	|
| /home/titan/Desktop/frames/test_detectron 	| Directorio de las imágenes de entrada 	|
- En el fichero [MODEL_ZOO.md](./MODEL_ZOO.md), se puede obtener la informacin para el resto de modelos implementados y disponibles en la carpeta `configs`.
Como ejemplo, la siguiente llamada utiliza un modelo End-to-end ms avanzado que utiliza la ResNext 101 en vez de la Resnet 101:
```
python2 tools/infer_simple_png.py \
    --cfg configs/12_2017_baselines/e2e_mask_rcnn_X-101-64x4d-FPN_1x.yaml \
    --output-dir /home/titan/data4Tb/videos/output \
    --image-ext png \
    --wts https://s3-us-west-2.amazonaws.com/detectron/36494496/12_2017_baselines/e2e_mask_rcnn_X-101-64x4d-FPN_1x.yaml.07_50_11.fkwVtEvg/output/train/coco_2014_train%3Acoco_2014_valminusminival/generalized_rcnn/model_final.pkl \
    /home/titan/Desktop/frames/test_detectron
```

