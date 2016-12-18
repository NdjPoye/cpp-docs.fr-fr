---
title: "_com_ptr_t::GetActiveObject | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t.GetActiveObject"
  - "_com_ptr_t::GetActiveObject"
  - "GetActiveObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetActiveObject (méthode)"
ms.assetid: 2fa94853-0410-4620-91f2-136dae923f9f
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_ptr_t::GetActiveObject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 S'attache à une instance existante d'un objet doté d'un **CLSID** ou **ProgID**.  
  
## Syntaxe  
  
```  
  
      HRESULT GetActiveObject(  
   const CLSID& rclsid   
) throw( );  
HRESULT GetActiveObject(  
   LPCWSTR clsidString   
) throw( );  
HRESULT GetActiveObject(  
   LPCSTR clsidStringA   
) throw( );  
```  
  
#### Paramètres  
 `rclsid`  
 **CLSID** d'un objet.  
  
 `clsidString`  
 Chaîne Unicode qui contient un **CLSID** \(commençant par « **{** »\) ou un **ProgID**.  
  
 `clsidStringA`  
 Chaîne multioctet, utilisant la page de codes ANSI, qui contient un **CLSID** \(commençant par « **{** »\) ou un **ProgID**.  
  
## Notes  
 Ces fonctions membres appellent `GetActiveObject` pour récupérer un pointeur vers un objet en cours d'exécution qui a été inscrit avec OLE, puis des requêtes pour le type d'interface de ce pointeur intelligent.  Le pointeur résultant est alors encapsulé dans cet objet `_com_ptr_t`.  **Release** est appelé pour décrémenter le décompte de références du pointeur précédemment encapsulé.  Cette routine retourne l'objet `HRESULT` pour indiquer un succès ou un échec.  
  
-   **GetActiveObject\(**  `rclsid`  **\)** S'attache à une instance existante d'un objet doté d'un **CLSID**.  
  
-   **GetActiveObject\(**  `clsidString`  **\)** S'attache à une instance existante d'un objet doté d'une chaîne Unicode qui contient un **CLSID** \(commençant par « **{** »\) ou un **ProgID**.  
  
-   **GetActiveObject\(**  `clsidStringA`  **\)** S'attache à une instance existante d'un objet doté d'une chaîne à caractères multioctets qui contient un **CLSID** \(commençant par « **{** »\) ou un **ProgID**.  Appelle [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072), qui suppose que la chaîne figure dans la page de codes ANSI plutôt que dans une page de codes OEM.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_com\_ptr\_t, classe](../cpp/com-ptr-t-class.md)