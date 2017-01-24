---
title: "AFX_EXTENSION_MODULE, structure | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "AFX_EXTENSION_MODULE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AFX_EXTENSION_MODULE (structure)"
ms.assetid: b85a989c-d0c5-4b28-b53c-dad45b75704e
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AFX_EXTENSION_MODULE, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`AFX_EXTENSION_MODULE` est utilisé lors de l'initialisation des DLL d'extension de MFC pour gérer l'état du module DLL d'extension.  
  
## Syntaxe  
  
```  
  
      struct AFX_EXTENSION_MODULE  
{  
   BOOL bInitialized;  
   HMODULE hModule;  
   HMODULE hResource;  
   CRuntimeClass* pFirstSharedClass;  
   COleObjectFactory* pFirstSharedFactory;  
};  
```  
  
#### Paramètres  
 *bInitialized*  
 **TRUE** si le module DLL a été initialisé avec `AfxInitExtensionModule`.  
  
 `hModule`  
 Spécifie le gestionnaire du module DLL.  
  
 *hRessource*  
 Spécifie le gestionnaire du module personnalisé de ressource DLL.  
  
 *pFirstSharedClass*  
 Un pointeur vers les informations \(la structure `CRuntimeClass` \) à propos de la première classe runtime du module.  Utilisé pour fournir le début de la liste de classe runtime.  
  
 *pFirstSharedFactory*  
 Un pointeur vers la première fabrique d'objet du module DLL \(objet de `COleObjectFactory` \).  Utilisé pour fournir le début de la liste de classe de fabrique.  
  
## Notes  
 Les DLL d'extension de MFC doivent avoir deux éléments dans leur fonction `DllMain` :  
  
-   Appelez [AfxInitExtensionModule](../Topic/AfxInitExtensionModule.md) et vérifiez la valeur de retour.  
  
-   Créez un objet de **CDynLinkLibrary** si la DLL exporte les objets de [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) ou possède ses propres ressources personnalisées.  
  
 La structure de `AFX_EXTENSION_MODULE` est utilisée pour conserver une copie de l'état du module DLL d'extension, y compris une copie des objets de classe runtime qui ont été initialisés par la DLL d'extension dans le contexte de la construction normale d'objets statique exécutée avant que `DllMain` soit entré.  Par exemple :  
  
 [!code-cpp[NVC_MFC_DLL#2](../../atl-mfc-shared/codesnippet/CPP/afx-extension-module-structure_1.cpp)]  
  
 Les informations du module stockées dans la structure de `AFX_EXTENSION_MODULE` peuvent être copiées dans l'objet de **CDynLinkLibrary**.  Par exemple :  
  
 [!code-cpp[NVC_MFC_DLL#5](../../atl-mfc-shared/codesnippet/CPP/afx-extension-module-structure_2.cpp)]  
  
## Configuration requise  
 **En\-tête :** afx.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [AfxInitExtensionModule](../Topic/AfxInitExtensionModule.md)   
 [AfxTermExtensionModule](../Topic/AfxTermExtensionModule.md)