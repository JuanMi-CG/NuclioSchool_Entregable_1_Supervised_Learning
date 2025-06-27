# 🚗 Proyecto de Supervised Learning - Data Science: Dataset de Coches BMW

## 📄 Descripción del Proyecto

El objetivo de este proyecto es estimar la probabilidad de que una máquina con Sistema Operativo Windows se vea infectada por algún tipo de malware, utilizando diversas propiedades de la máquina. Este proyecto se basa en el dataset original de la competición de Kaggle [Microsoft Malware Prediction](https://www.kaggle.com/c/microsoft-malware-prediction). Los datos provienen de las características recolectadas por la solución de endpoint Windows Defender.

Cada registro en el dataset representa una máquina única, identificada por el campo `MachineIdentifier`, y el objetivo principal es predecir la variable `HasDetections`, que indica si se ha detectado malware en la máquina.

## Objetivos

1. **Desarrollar el ML Canvas**: Plantear un marco de trabajo para el modelo que será utilizado en la aplicación Windows Defender, con el fin de alertar al usuario cuando la probabilidad de infección supere un umbral determinado.
2. **Crear un Notebook de modelo**: Desarrollar un Notebook que contenga todas las etapas necesarias para resolver el problema, siguiendo la ML Checklist. Este Notebook debe realizar la exploración de datos, preprocesamiento, modelado mediante un Decision Tree y un Random Forest, y la evaluación del modelo.

## Contenido del Notebook

El Notebook sigue las etapas esenciales de un proyecto de Ciencia de Datos:

1. **Data Understanding**: Análisis y comprensión inicial de los datos disponibles.
2. **Data Preprocessing**: Limpieza y transformación de los datos para prepararlos para el modelado.
3. **Benchmarking**: Establecimiento de una línea base de rendimiento del modelo.
4. **Modeling**: Creación y entrenamiento de modelos predictivos, empezando con un Decision Tree.
5. **Evaluation**: Evaluación del rendimiento del modelo utilizando métricas apropiadas y análisis de los resultados.

El proceso comienza con la comprensión de los datos, seguida de la preparación, modelado y evaluación del rendimiento del modelo.

## 📚 Índice de contenidos

- 1. Trabajo Previo 📋
  - 1.1. Introducción 🌟
  - 1.2. Objetivos 🎯
  - 1.3. Contenido del Notebook 📒
  - 1.4. Import libraries 📚
  - 1.5. Establecer estilos 🎨
  - 1.6. Import data 📈
  - 1.7. Funciones 🔧
  - 1.8. Listas 📜
- 2. Data understanding 📊
  - 2.1. Tamaño del dataset 📏
  - 2.2. Tipo de atributos disponibles 📝
  - 2.3. Nulos 🚫
    - 2.3.1. Eliminar Nulos en Target 🗑️
    - 2.3.2. Resto de Nulos 🗃️
  - 2.4. Target 🎯
  - 2.5. Categóricas 🗂️
    - 2.5.1. MachineIdentifier 🔢
    - 2.5.2. ProductName 🏷️
    - 2.5.3. EngineVersion 🛠️
    - 2.5.4. AppVersion 📱
    - 2.5.5. AvSigVersion 🔍
    - 2.5.6. Platform 🖥️
    - 2.5.7. Processor 🧠
    - 2.5.8. OsVer 💾
    - 2.5.9. OsPlatformSubRelease 🚀
    - 2.5.10. OsBuildLab 🏭
    - 2.5.11. SkuEdition 📦
    - 2.5.12. Census_OSArchitecture 🏛️
    - 2.5.13. Census_OSBranch 🌿
    - 2.5.14. Census_OSSkuName 🏷️
    - 2.5.15. Census_OSInstallTypeName ⚙️
    - 2.5.16. Census_OSWUAutoUpdateOptionsName 🔄
    - 2.5.17. Census_IsPortableOperatingSystem 📲
    - 2.5.18. Census_GenuineStateName 🏷️
    - 2.5.19. Census_ActivationChannel 🚪
    - 2.5.20. Census_FlightRing ✈️
    - 2.5.21. Census_IsPenCapable 🖊️
    - 2.5.22. Census_IsFlightingInternal ✈️
    - 2.5.23. Census_IsFlightsDisabled 🚫
    - 2.5.24. Census_FirmwareManufacturerIdentifier 🏭
    - 2.5.25. Census_FirmwareVersionIdentifier 🔢
    - 2.5.26. Census_IsTouchEnabled 🖐️
    - 2.5.27. IeVerIdentifier 🌐
    - 2.5.28. SmartScreen 🛡️
    - 2.5.29. Census_MDC2FormFactor 🖥️
    - 2.5.30. Census_OEMNameIdentifier 🏭
    - 2.5.31. Census_OEMModelIdentifier 🔢
    - 2.5.32. Census_ProcessorManufacturerIdentifier 🏭
    - 2.5.33. Census_ProcessorModelIdentifier 🔢
    - 2.5.34. Census_ProcessorClass 🧠
    - 2.5.35. Census_PrimaryDiskTypeName 💽
    - 2.5.36. Census_ChassisTypeName 💼
    - 2.5.37. Census_PowerPlatformRoleName ⚡
    - 2.5.38. Census_InternalBatteryType 🔋
    - 2.5.39. Census_OSVersion 💾
  - 2.6. Numericas 🔢
    - 2.6.1. IsBeta 🧪
    - 2.6.2. RtpStateBitfield 📊
    - 2.6.3. IsSxsPassiveMode 🛑
    - 2.6.4. AVProductStatesIdentifier 🔒
    - 2.6.5. AVProductsInstalled 🛠️
    - 2.6.6. AVProductsEnabled 🔓
    - 2.6.7. HasTpm 🔐
    - 2.6.8. CountryIdentifier 🗺️
    - 2.6.9. CityIdentifier 🏙️
    - 2.6.10. OrganizationIdentifier 🏢
    - 2.6.11. GeoNameIdentifier 🌐
    - 2.6.12. LocaleEnglishNameIdentifier 🏴
    - 2.6.13. OsBuild 🔧
    - 2.6.14. OsSuite 🛠️
    - 2.6.15. IsProtected 🛡️
    - 2.6.16. PuaMode 🛑
    - 2.6.17. UacLuaenable 🔓
    - 2.6.18. Census_DeviceFamily 👨‍👩‍👧‍👦
    - 2.6.19. Census_ProcessorCoreCount 🧠
    - 2.6.20. Census_PrimaryDiskTotalCapacity 💽
    - 2.6.21. Census_SystemVolumeTotalCapacity 💾
    - 2.6.22. Census_TotalPhysicalRAM 🧠
    - 2.6.23. Census_InternalPrimaryDiagonalDisplaySizeInInches 📏
    - 2.6.24. Census_InternalPrimaryDisplayResolutionHorizontal 📐
    - 2.6.25. Census_InternalPrimaryDisplayResolutionVertical 📏
    - 2.6.26. Census_InternalBatteryNumberOfCharges 🔋
    - 2.6.27. Census_OSBuildNumber 🔧
    - 2.6.28. Census_OSBuildRevision 🛠️
    - 2.6.29. Census_OSEdition 💾
    - 2.6.30. Census_OSInstallLanguageIdentifier 🌐
    - 2.6.31. Census_OSUILocaleIdentifier 🌐
    - 2.6.32. Census_IsSecureBootEnabled 🔐
    - 2.6.33. Census_OSInstallLanguageIdentifier 🌐
    - 2.6.34. Census_ThresholdOptIn 🔄
    - 2.6.35. Census_IsWIMBootEnabled 🚀
    - 2.6.36. Census_IsVirtualDevice 🖥️
    - 2.6.37. Census_IsAlwaysOnAlwaysConnectedCapable 🔋
    - 2.6.38. Wdft_IsGamer 🎮
    - 2.6.39. Wdft_RegionIdentifier 🗺️
    - 2.6.40. AutoSampleOptIn 📊
    - 2.6.41. SMode 🔒
    - 2.6.42. Firewall 🔥
    - 2.6.43. Census_HasOpticalDiskDrive 💿
  - 2.7. Conclusiones del Data Understanding 📝
- 3. Benchmark 🏁
  - 3.1.1. Preparación del Benchmark 🛠️
  - 3.1.2. Split en Train y Test ✂️
  - 3.1.3. Transformaciones 🔄
    - 3.1.3.1. Características Principales ⭐
  - 3.1.4. Modelaje 🧠
  - 3.1.5. Scoring del Benchmark 📈
- 4. Data preparation 🧹
  - 4.1.1. Transformación OHE 🔧
  - 4.1.2. Split en Train y Test ✂️
- 5. Modelaje 🧠
  - 5.1. Decision Tree 🌳
    - 5.1.1. Nivel de profundidad 🌱
    - 5.1.2. Entrenamiento definitivo 🎓
    - 5.1.3. Predicciones Test 🧪
    - 5.1.4. Predicciones Validacion 🧪
    - 5.1.5. Scoring del Decision Tree 📈
  - 5.2. Random Forest 🌲
    - 5.2.1. Nivel de profundidad 🌱
    - 5.2.2. Ajuste de estimadores ⚙️
    - 5.2.3. Entrenamiento definitivo 🎓
    - 5.2.4. Predicciones Test 🧪
    - 5.2.5. Predicciones Validacion 🧪
    - 5.2.6. Scoring del Random Forest 📈
- 6. Análisis de Resultados 🔍
  - 6.1. Top Features ⭐
  - 6.2. Metricas 📏
 - 6.3. Optimizaciones posibles 🛠️
  - 6.4. Conclusiones 📝
- 7. Guardar el modelo 💾

## 🗂️ Estructura del Proyecto

El proyecto está estructurado en varias secciones, cada una enfocada en un aspecto específico del preprocesamiento de datos. 

1. **🗑️ Eliminación de Columnas**
   - Se identificaron y eliminaron columnas irrelevantes para el análisis.
2. **🧹 Manejo de Valores Nulos**
   - Se trató y limpió las columnas con valores nulos.
3. **📊 Análisis Univariable**
   - Se realizó un análisis univariable para detectar outliers y posibles agrupaciones.
4. **🔗 Análisis de Correlación Inicial**
   - Se realizó un análisis de correlación inicial para identificar variables correlacionadas.
5. **🔍 Análisis Variable vs Target**
   - Se analizó la relación entre las variables y el target (precio del vehículo) para identificar insights interesantes.
6. **🔢 Transformación de Categóricas a Numéricas**
   - Se transformaron las variables categóricas a numéricas utilizando técnicas adecuadas.
7. **⚖️ Normalización de Variables Numéricas**
   - Se normalizaron las variables numéricas.
8. **🔗 Análisis de Correlación Final**
   - Se realizó un análisis de correlación final para observar los cambios después del preprocesamiento.
9. **📋 Dataset Limpio y Preprocesado**
   - Se presentó la lista completa de columnas del dataset limpio y preprocesado, incluyendo el tipo de dato de cada columna y un pantallazo de las primeras 5 líneas.

## 📁 Estructura de Carpetas

- **datasets/**: Contiene el dataset de coches BMW.
  - `sample_mmp.csv`
- **images/**: Contiene las imagenes generadas en el entregable.
  - `dt_tree.png`
  - `rf_tree.png`
- **models/**: Contiene el los modelos utilizados en el entregable.
  - `dt_model.pkl`
  - `rf_model.pkl`
- **notebooks/**: Contiene los notebooks utilizados durante el desarrollo del proyecto.
  - `Entregable_2_Supervised_Learning.ipynb`
- **outputs/**: Contiene el resto de archivos de salida del proyecto.
  - `resumen.csv`

## 🔧 Requisitos

- Python 3.x
- Librerías y módulos necesarios:
  - `os`
  - `numpy`
  - `pandas`
  - `matplotlib`
  - `seaborn`
  - `graphviz`
  - `pydotplus`
  - `pickle`
  - `scikit-learn`

## 🚀 Instrucciones

1. Clonar el repositorio.
   
    ```
    git clone https://github.com/JuanMi-CG/NuclioSchool_Entregable_1_Supervised_Learning.git
    ```

2. Asegúrate de tener Graphviz instalado.
    [Descargar Graphviz](https://graphviz.org/download/)

