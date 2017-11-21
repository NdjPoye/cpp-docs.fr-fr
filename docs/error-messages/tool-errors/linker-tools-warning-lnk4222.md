---
title: "LNK4222 d’avertissement des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4222
dev_langs: C++
helpviewer_keywords: LNK4222
ms.assetid: b7bb1794-41fb-4c83-b9b0-59c0d786a7da
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a0074e71902a145df8c37b52a5a16295a2b1dfd2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-warning-lnk4222"></a>Avertissement des outils Éditeur de liens LNK4222
un symbole exporté 'symbole' ne doit pas être attribué un ordinal  
  
 Les symboles suivants ne doivent pas être exportés par ordinal :  
  
-   `DllCanUnloadNow`  
  
-   `DllGetClassObject`  
  
-   `DllGetClassFactoryFromClassString`  
  
-   `DllInstall`  
  
-   `DllRegisterServer`  
  
-   `DllRegisterServerEx`  
  
-   `DllUnregisterServer`  
  
 Ces fonctions sont toujours situées par nom, à l’aide de `GetProcAddress`. L’éditeur de liens vous avertit sur ce type d’exportation est, car elle peut entraîner une image plus grande. Cela peut se produire si la plage de vos exportations ordinales est grande avec relativement peu d’exportations. Par exemple :  
  
```  
EXPORTS  
   DllGetClassObject   @1  
   MyOtherAPI      @100  
```  
  
 nécessite 100 emplacements dans la table d’adresses exportation dont 98 remplisseur simplement de (2-99). D'un autre côté  
  
```  
EXPORTS  
   DllGetClassObject  
   MyOtherAPI      @100  
```  
  
 nécessite deux emplacements. (Sachez que vous pouvez également exporter avec la [/EXPORT](../../build/reference/export-exports-a-function.md) option de l’éditeur de liens.)