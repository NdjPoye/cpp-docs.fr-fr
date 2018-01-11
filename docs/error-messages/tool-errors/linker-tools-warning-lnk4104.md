---
title: "LNK4104 d’avertissement des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4104
dev_langs: C++
helpviewer_keywords: LNK4104
ms.assetid: ca6728db-d616-419a-a570-65e8445c6079
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b26286f375f54a20e1d3db534576f692179ade24
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4104"></a>Avertissement des outils Éditeur de liens LNK4104
l’exportation du symbole 'symbole' doit être PRIVATE  
  
 Le `symbol` peut prendre l’une des opérations suivantes :  
  
-   `DllCanUnloadNow`  
  
-   `DllGetClassObject`  
  
-   `DllGetClassFactoryFromClassString`  
  
-   `DllGetDocumentation`  
  
-   `DllInitialize`  
  
-   `DllInstall`  
  
-   `DllRegisterServer`  
  
-   `DllRegisterServerEx`  
  
-   `DllRegisterServerExW`  
  
-   `DllUnload`  
  
-   `DllUnregisterServer`  
  
-   `RasCustomDeleteEntryNotify`  
  
-   `RasCustomDial`  
  
-   `RasCustomDialDlg`  
  
-   `RasCustomEntryDlg`  
  
 Cet avertissement est émis lorsque vous créez une bibliothèque d’importation pour une DLL et exporter une des fonctions ci-dessus sans spécifier comme privée dans le fichier de définition de module. En règle générale, ces fonctions sont exportées pour une utilisation uniquement par OLE. En les plaçant dans la bibliothèque d’importation peuvent entraîner un comportement inhabituel lorsqu’un programme lié à la bibliothèque de manière incorrecte émet des appels. Pour plus d’informations sur le mot clé privé, consultez [exportations](../../build/reference/exports.md).