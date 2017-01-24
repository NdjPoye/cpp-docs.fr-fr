---
title: "_variant_t::operator = | Microsoft Docs"
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
  - "_variant_t.operator="
  - "_variant_t::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "= (opérateur), avec des objets Visual C++ spécifiques"
  - "= (opérateur), variante"
  - "= (opérateur), variante"
ms.assetid: 77622723-6e49-4dec-9e0f-fa74028f1a3c
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _variant_t::operator =
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
## Syntaxe  
  
```  
  
      _variant_t& operator=(  
   const VARIANT& varSrc   
);  
  
_variant_t& operator=(  
   const VARIANT* pVarSrc   
);  
  
_variant_t& operator=(  
   const _variant_t& var_t_Src   
);  
  
_variant_t& operator=(  
   short sSrc   
);  
  
_variant_t& operator=(  
   long lSrc   
);  
  
_variant_t& operator=(  
   float fltSrc   
);  
  
_variant_t& operator=(  
   double dblSrc   
);  
  
_variant_t& operator=(  
   const CY& cySrc   
);  
  
_variant_t& operator=(  
   const _bstr_t& bstrSrc   
);  
  
_variant_t& operator=(  
   const wchar_t* wstrSrc   
);  
  
_variant_t& operator=(  
   const char* strSrc   
);  
  
_variant_t& operator=(  
   IDispatch* pDispSrc   
);  
  
_variant_t& operator=(  
   bool bSrc   
);  
  
_variant_t& operator=(  
   IUnknown* pSrc   
);  
  
_variant_t& operator=(  
   const DECIMAL& decSrc   
);  
  
_variant_t& operator=(  
   BYTE bSrc   
);  
  
_variant_t& operator=(  
   char cSrc  
);  
  
_variant_t& operator=(  
   unsigned short usSrc  
);  
  
_variant_t& operator=(  
   unsigned long ulSrc  
);  
  
_variant_t& operator=(  
   int iSrc  
);  
  
_variant_t& operator=(  
   unsigned int uiSrc  
);  
  
_variant_t& operator=(  
   __int64 i8Src  
);  
  
_variant_t& operator=(  
   unsigned __int64 ui8Src  
);  
```  
  
## Notes  
 L'opérateur assigne une nouvelle valeur à l'objet `_variant_t` :  
  
-   **operator\=\(**  *varSrc*  **\)** Assigne un objet **VARIANT** existant à un objet `_variant_t`.  
  
-   **operator\=\(**  *pVarSrc*  **\)** Assigne un objet **VARIANT** existant à un objet `_variant_t`.  
  
-   **operator\=\(**  *var\_t\_Src*  **\)** Assigne un objet `_variant_t` existant à un objet `_variant_t`.  
  
-   **operator\=\(**  *sSrc*  **\)** Assigne une valeur entière **short** à un objet `_variant_t`.  
  
-   **operator\=\(**  `lSrc`  **\)** Assigne une valeur entière **long** à un objet `_variant_t`.  
  
-   **operator\=\(**  *fltSrc*  **\)** Assigne une valeur numérique **float** à un objet `_variant_t`.  
  
-   **operator\=\(**  *dblSrc*  **\)** Assigne une valeur numérique **double** à un objet `_variant_t`.  
  
-   **operator\=\(**  *cySrc*  **\)** Assigne un objet **CY** à un objet `_variant_t`.  
  
-   **operator\=\(**  *bstrSrc*  **\)** Assigne un objet `BSTR` à un objet `_variant_t`.  
  
-   **operator\=\(**  *wstrSrc*  **\)** Assigne une chaîne Unicode à un objet `_variant_t`.  
  
-   **operator\=\(**  `strSrc`  **\)** Assigne une chaîne multioctets à un objet `_variant_t`.  
  
-   **operator\=\(**  `bSrc` **\)** Assigne une valeur `bool` à un objet `_variant_t`.  
  
-   **operator\=\(**  *pDispSrc*  **\)** Assigne un objet **VT\_DISPATCH** à un objet `_variant_t`.  
  
-   **operator\=\(**  *pIUnknownSrc*  **\)** Assigne un objet **VT\_UNKNOWN** à un objet `_variant_t`.  
  
-   **operator\=\(**  *decSrc*  **\)** Assigne une valeur **DECIMAL** à un objet `_variant_t`.  
  
-   **operator\=\(**  `bSrc` **\)** Assigne une valeur **BYTE** à un objet `_variant_t` .  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_variant\_t \(classe\)](../cpp/variant-t-class.md)