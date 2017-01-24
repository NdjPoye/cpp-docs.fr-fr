---
title: "__outwordstring | Microsoft Docs"
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
  - "__outwordstring"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rep outsw, instruction"
  - "__outwordstring, intrinsèque"
  - "outsw, instruction"
ms.assetid: b470c7a0-1de9-4370-886a-b2c3a1f842f4
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __outwordstring
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Génère des instructions d' `rep outsw` , qui envoie des mots d' `Count` en commençant à l'adresse `Buffer` le port d'E\/S spécifié par `Port`.  
  
## Syntaxe  
  
```  
void __outwordstring(   
   unsigned short Port,   
   unsigned short* Buffer,   
   unsigned long Count   
);  
```  
  
#### Paramètres  
 \[in\] `Port`  
 Le port pour renvoyer les données à.  
  
 \[in\] `Buffer`  
 Un pointeur vers les données à envoyer le port spécifié.  
  
 \[in\] `Count`  
 le nombre de mots à les envoyer.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__outwordstring`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Cette routine est uniquement disponible sous forme intrinsèque.  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)