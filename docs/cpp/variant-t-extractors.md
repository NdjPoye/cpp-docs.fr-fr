---
title: "Extracteurs _variant_t | Microsoft Docs"
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
  - "_variant_t.operatordouble"
  - "operatorlong"
  - "_variant_t::operator_bstr_t"
  - "operatordouble"
  - "_variant_t.operatorCY"
  - "operatorCY"
  - "_variant_t::operatorCY"
  - "_variant_t::operatordouble"
  - "operatorfloat"
  - "operatorBYTE"
  - "_variant_t.operatorDECIMAL"
  - "_variant_t::operatorlong"
  - "operatorIDispatch"
  - "_variant_t.operatorBYTE"
  - "operatorDECIMAL"
  - "_variant_t.operator_bstr_t"
  - "_variant_t::operatorDECIMAL"
  - "_variant_t.operatorIUnknown"
  - "_variant_t.operatorlong"
  - "_variant_t::operatorIDispatch"
  - "_variant_t::operatorIUnknown"
  - "operatorIUnknown"
  - "_variant_t.operatorbool"
  - "_variant_t::operatorBYTE"
  - "_variant_t.operatorfloat"
  - "operator_bstr_t"
  - "_variant_t::operatorbool"
  - "operatorshort"
  - "_variant_t::operatorshort"
  - "_variant_t::operatorfloat"
  - "_variant_t.operatorIDispatch"
  - "_variant_t.operatorshort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "extracteurs, _variant_t (classe)"
  - "_bstr_t (opérateur)"
  - "bool (opérateur)"
  - "BYTE (opérateur)"
  - "CY (opérateur)"
  - "DECIMAL (opérateur)"
  - "double (opérateur)"
  - "float (opérateur)"
  - "IDispatch (opérateur)"
  - "IUnknown (opérateur)"
  - "long (opérateur)"
  - "opérateur SHORT"
ms.assetid: 33c1782f-045a-4673-9619-1d750efc83a9
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Extracteurs _variant_t
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Extrait des données de l'objet **VARIANT** encapsulé.  
  
## Syntaxe  
  
```  
  
      operator short( ) const;   
operator long( ) const;   
operator float( ) const;   
operator double( ) const;   
operator CY( ) const;   
operator _bstr_t( ) const;   
operator IDispatch*( ) const;   
operator bool( ) const;   
operator IUnknown*( ) const;   
operator DECIMAL( ) const;   
operator BYTE( ) const;  
operator VARIANT() const throw();  
operator char() const;  
operator unsigned short() const;  
operator unsigned long() const;  
operator int() const;  
operator unsigned int() const;  
operator __int64() const;  
operator unsigned __int64() const;  
```  
  
## Notes  
 Extrait des données brutes d'un objet **VARIANT**encapsulé.  Si **VARIANT** n'est pas encore le type approprié, **VariantChangeType** est utilisé pour effectuer une conversion et une erreur est générée en cas d'échec :  
  
-   **operator short\( \)** Extrait une valeur entière **short**.  
  
-   **operator long\( \)** Extrait une valeur entière **long**.  
  
-   **operator float\( \)** Extrait une valeur numérique **float**.  
  
-   **operator double\( \)** Extrait une valeur entière **double**.  
  
-   **operator CY\( \)** Extrait un objet **CY**.  
  
-   **operator bool\( \)** Extrait une valeur `bool`.  
  
-   **operator DECIMAL\( \)** Extrait une valeur **DECIMAL**.  
  
-   **operator BYTE\( \)** Extrait une valeur **BYTE**.  
  
-   **operator \_bstr\_t\( \)** Extrait une chaîne, qui est encapsulée dans un objet `_bstr_t`.  
  
-   **operator IDispatch\*\( \)** Extrait un pointeur dispinterface d'un objet **VARIANT**encapsulé.  `AddRef` est appelé sur le pointeur résultant. Il vous appartient donc d'appeler **Release** pour le libérer.  
  
-   **operator IUnknown\*\( \)** Extrait un pointeur d'interface COM d'un objet **VARIANT**encapsulé.  `AddRef` est appelé sur le pointeur résultant. Il vous appartient donc d'appeler **Release** pour le libérer.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_variant\_t \(classe\)](../cpp/variant-t-class.md)