---
title: "Avertissement des outils &#201;diteur de liens LNK4222 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4222"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4222"
ms.assetid: b7bb1794-41fb-4c83-b9b0-59c0d786a7da
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Avertissement des outils &#201;diteur de liens LNK4222
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

un symbole exporté 'symbole' ne doit pas se voir assigner un nombre ordinal  
  
 Les symboles ci\-dessous ne doivent pas être exportés par un nombre ordinal :  
  
-   `DllCanUnloadNow`  
  
-   `DllGetClassObject`  
  
-   `DllGetClassFactoryFromClassString`  
  
-   `DllInstall`  
  
-   `DllRegisterServer`  
  
-   `DllRegisterServerEx`  
  
-   `DllUnregisterServer`  
  
 Ces fonctions sont toujours situées par nom, en utilisant `GetProcAddress`.  L'éditeur de liens vous avertit de ce type d'exportation parce qu'il peut créer une image résultante de taille plus grande.  Ceci peut se produire si la plage de vos exportations ordinales est grande avec relativement peu d'exportations.  Par exemple :  
  
```  
EXPORTS  
   DllGetClassObject   @1  
   MyOtherAPI      @100  
```  
  
 nécessite 100 emplacements dans la table d'adresses d'exportation, dont 98 \(2\-99\) ne sont que du remplissage.  Par contre,  
  
```  
EXPORTS  
   DllGetClassObject  
   MyOtherAPI      @100  
```  
  
 nécessite deux emplacements. \(Vous devez savoir qu'il est aussi possible d'exporter par l'option de l'éditeur de liens [\/EXPORT](../../build/reference/export-exports-a-function.md)\).