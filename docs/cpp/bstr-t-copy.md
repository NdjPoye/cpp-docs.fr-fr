---
title: "_bstr_t::copy | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_bstr_t::copy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BSTR (objet), copier"
  - "Copy (méthode)"
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _bstr_t::copy
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Construit une copie du `BSTR` encapsulé.  
  
## Syntaxe  
  
```  
  
      BSTR copy(  
  bool fCopy = true  
) const;  
```  
  
#### Paramètres  
 `fCopy`  
 Si la valeur est **true**, **copy** retourne une copie du `BSTR` contenu, sinon **copy** retourne le BSTR réel.  
  
## Notes  
 Retourne une copie nouvellement allouée de l'objet `BSTR` encapsulé.  
  
## Exemple  
  
```  
STDMETHODIMP CAlertMsg::get_ConnectionStr(BSTR *pVal){ //  m_bsConStr is _bstr_t  
   *pVal = m_bsConStr.copy();  
}  
```  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_bstr\_t, classe](../cpp/bstr-t-class.md)