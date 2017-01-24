---
title: "_com_ptr_t::CreateInstance | Microsoft Docs"
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
  - "_com_ptr_t::CreateInstance"
  - "_com_ptr_t.CreateInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateInstance (méthode)"
ms.assetid: ab89b0e1-9da3-4784-a079-58b17340f111
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_ptr_t::CreateInstance
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Crée une nouvelle instance d'un objet avec un **CLSID** ou **ProgID**.  
  
## Syntaxe  
  
```  
  
      HRESULT CreateInstance(  
   const CLSID& rclsid,  
   IUnknown* pOuter=NULL,  
   DWORD dwClsContext = CLSCTX_ALL   
) throw( );  
HRESULT CreateInstance(  
   LPCWSTR clsidString,  
   IUnknown* pOuter=NULL,  
   DWORD dwClsContext = CLSCTX_ALL   
) throw( );  
HRESULT CreateInstance(  
   LPCSTR clsidStringA,  
   IUnknown* pOuter=NULL,  
   DWORD dwClsContext = CLSCTX_ALL   
) throw( );  
```  
  
#### Paramètres  
 `rclsid`  
 **CLSID** d'un objet.  
  
 `clsidString`  
 Chaîne Unicode qui contient un **CLSID** \(commençant par « **{** »\) ou un **ProgID**.  
  
 `clsidStringA`  
 Chaîne multioctet, utilisant la page de codes ANSI, qui contient un **CLSID** \(commençant par « **{** »\) ou un **ProgID**.  
  
 `dwClsContext`  
 Contexte d'exécution du code exécutable.  
  
 `pOuter`  
 Inconnu externe pour l'[agrégation](../atl/aggregation.md).  
  
## Notes  
 Ces fonctions membres appellent `CoCreateInstance` pour créer un objet COM puis des requêtes pour le type d'interface de ce pointeur intelligent.  Le pointeur résultant est alors encapsulé dans cet objet `_com_ptr_t`.  **Release** est appelé pour décrémenter le décompte de références du pointeur précédemment encapsulé.  Cette routine retourne l'objet `HRESULT` pour indiquer un succès ou un échec.  
  
-   **CreateInstance\(**  `rclsid` **,**  `dwClsContext`  **\)** Crée une instance d'exécution d'un objet en fonction d'un **CLSID**.  
  
-   **CreateInstance\(**  `clsidString` **,**  `dwClsContext`  **\)** Crée une instance d'exécution d'un objet en fonction d'une chaîne Unicode qui contient un **CLSID** \(commençant par « **{** »\) ou un **ProgID**.  
  
-   **CreateInstance\(**  `clsidStringA` **,**  `dwClsContext`  **\)** Crée une instance d'exécution d'un objet en fonction d'une chaîne de caractères multioctets qui contient un **CLSID** \(commençant par « **{** »\) ou un **ProgID**.  Appelle [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072), qui suppose que la chaîne figure dans la page de codes ANSI plutôt que dans une page de codes OEM.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_com\_ptr\_t, classe](../cpp/com-ptr-t-class.md)