---
title: "SEGMENT | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SEGMENT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SEGMENT directive"
ms.assetid: e6f68367-6714-4f06-a79c-edfa88014430
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# SEGMENT
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit un segment de programme appelé *nom* avaient des attributs de segment  
  
## Syntaxe  
  
```  
  
   name SEGMENT [[READONLY]] [[align]] [[combine]] [[use]] [[characteristics]] ALIAS(string) [['class']]  
statements  
name ENDS  
```  
  
#### Paramètres  
 *aligner*  
 Les adresses de gamme de mémoire dont une adresse de départ pour le segment peut être sélectionnée.  Le type d'alignement peut être tout l'un des éléments suivants :  
  
|alignez le type|Démarrer l'adresse|  
|---------------------|------------------------|  
|**BYTE**|adresse d'octet disponible suivante.|  
|**WORD**|adresse de mot disponible suivante \(2 octets par mot\).|  
|**DWORD**|adresse de double mot disponible suivante \(4 octets par double mot\).|  
|**PARA**|Adresse suivante disponible de paragraphe \(16 octets par paragraphe\).|  
|**PG**|Adresse de la page suivante disponible \(256 octets par page\).|  
|**ALIGNER**\(n\)|*Nth*adresse d'octet disponible suivante.  Consultez la section Notes pour plus d'informations.|  
  
 si ce paramètre n'est pas spécifié, **PARA** est utilisé par défaut.  
  
 *combine*  
 **PUBLIC**, **PILE**, **COMMUN**, **MÉMOIRE**,*adresse de***À**, **PRIVATE**  
  
 *utilisation*  
 **USE16**, **USE32**, **APPARTEMENT**  
  
 `characteristics`  
 **INFORMATIONS**, **LECTURE**, **ÉCRITURE**, **EXÉCUTER**, **PARTAGÉ**, **NOPAGE**, **NOCACHE**, et **ABANDONNER**  
  
 Celles\-ci sont prises en charge pour COFF uniquement et correspondent aux spécifications de section COFF du nom similaire \(par exemple, **PARTAGÉ** correspond à IMAGE\_SCN\_MEM\_SHARED\).  La LECTURE définit la balise d'IMAGE\_SCN\_MEM\_READ.  La balise READONLY obsolète a effectué pour désactiver la section la balise d'IMG\_SCN\_MEM\_WRITE.  Si tout `characteristics` sont définis, les caractéristiques par défaut ne sont pas utilisées et seuls les balises programmeur\-spécifiées sont activées.  
  
 `ALIAS(` `string` `)`  
 Cette chaîne est utilisée comme nom de section dans l'objet émis COFF.  Crée plusieurs sections avec le même nom externe, avec les noms du segment distincts MASM.  
  
 non pris en charge avec **\/omf**.  
  
 `class`  
 Indique comment les segments doivent être combinés et classés dans le fichier assemblé.  Les valeurs classiques sont, `'DATA'`, `'CODE'`, `'CONST'` et `'STACK'`  
  
## Notes  
 Pour `ALIGN(``n``)`, `n` peut être une puissance de 2 entre 1 et 8192 ; non pris en charge avec **\/omf**.  
  
## Voir aussi  
 [Directives Reference](../../assembler/masm/directives-reference.md)