---
title: "Classes et fonctions g&#233;n&#233;r&#233;es par l&#39;Assistant DLL MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes (C++), généré par l'Assistant DLL MFC"
  - "code (C++), généré par l'Assistant DLL MFC"
  - "DLL (C++), fonctions et classes de l'Assistant"
  - "fonctions (MFC)"
  - "fonctions (MFC), DLL"
  - "DLL MFC (Assistant)"
ms.assetid: e69e62fe-4953-42bf-a2fc-50bbf9bdaeaf
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Classes et fonctions g&#233;n&#233;r&#233;es par l&#39;Assistant DLL MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le code généré par l'Assistant DLL MFC dépend du type de DLL que vous créez et des options sélectionnées.  L'Assistant DLL MFC génère le même code pour les deux formes de DLL normales.  
  
|Type de DLL|Option|Classes|Fonctions|  
|-----------------|------------|-------------|---------------|  
|[Extension](../../build/extension-dlls-overview.md)|None|None|`DllMain`|  
|[Normale](../../build/regular-dlls-dynamically-linked-to-mfc.md)|None|Classe d'application dérivée de `CWinApp`|None|  
|[Normale](../../build/regular-dlls-dynamically-linked-to-mfc.md)|Automation|Classe d'application dérivée de `CWinApp`|**DllGetClassObjectDllCanUnloadNowDllRegisterServer**|  
|[Extension](../../build/extension-dlls-overview.md)|Windows Sockets|None|`DllMain`|  
|[Normale](../../build/regular-dlls-dynamically-linked-to-mfc.md)|Windows Sockets|Classe d'application dérivée de `CWinApp`|`InitInstance`contient des appels à `AfxSocketInit`|  
  
## Voir aussi  
 [DLL MFC \(Assistant\)](../../mfc/reference/mfc-dll-wizard.md)