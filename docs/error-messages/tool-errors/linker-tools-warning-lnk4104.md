---
title: "Avertissement des outils &#201;diteur de liens LNK4104 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4104"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4104"
ms.assetid: ca6728db-d616-419a-a570-65e8445c6079
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Avertissement des outils &#201;diteur de liens LNK4104
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

l'exportation du symbole 'symbole' doit être PRIVATE  
  
 Le `symbol` peut être un des suivants :  
  
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
  
 Cet avertissement est émis quand vous générez une bibliothèque d'importation pour une DLL et que vous exportez une des fonctions ci\-dessus sans la spécifier comme PRIVATE dans le fichier de définition de module.  En général, ces fonctions ne sont exportées que pour utilisation par OLE.  Les placer dans la bibliothèque d'importation peut conduire à un comportement inhabituel quand un programme lié à la bibliothèque fait des appels incorrects à ces fonctions.  Pour plus d'informations sur le mot clé PRIVATE, consultez [EXPORTS](../../build/reference/exports.md).