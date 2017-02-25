---
title: "Understanding Backus Nauer Form (BNF) Syntax | Microsoft Docs"
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
  - "Backus Nauer Form (BNF) syntax"
  - "BNF notation"
ms.assetid: 994bbef0-9077-4aa8-bdfe-b7e830af9acc
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Understanding Backus Nauer Form (BNF) Syntax
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les scripts utilisés par ATL Registrar sont décrits dans cette rubrique à l'aide de la syntaxe BNF de, qui utilise la notation indiqué dans le tableau suivant.  
  
|Convention\/symboles|Signification|  
|--------------------------|-------------------|  
|`::=`|Équivalent|  
|`&#124;`|OR|  
|`X+`|Un ou plusieurs `X`S.|  
|`[X]`|`X` est facultatif.  Les séparateurs facultatifs sont dénotés par `[]`.|  
|Tout caractère gras|Un littéral de chaîne.|  
|Tout *texte en italique*|Construisez procédure le littéral de chaîne.|  
  
 Comme indiqué dans le tableau précédent, les scripts d'inscription utilisent des littéraux de chaîne.  Ces valeurs sont un texte réel qui doit apparaître dans votre script.  Le tableau suivant décrit les littéraux de chaîne utilisés dans un script ATL Registrar.  
  
|Littéral de chaîne|Action|  
|------------------------|------------|  
|**ForceRemove**|Supprimer complètement la prochaine clé \(si elle existe\) et la recrée ensuite.|  
|**NoRemove**|Ne supprime pas la prochaine clé pendant annulent l'enregistrement.|  
|**val**|Spécifie qu' `<Key Name>` est en fait une valeur nommée.|  
|**Supprimer**|Supprime la prochaine clé pendant le registre.|  
|**s**|Spécifie que la prochaine valeur est une chaîne \(**REG\_SZ**\).|  
|**d**|Spécifie que la prochaine valeur est **DWORD** \(**REG\_DWORD**\).|  
|**m**|Spécifie que la prochaine valeur est une à plusieurs chaînes \(**REG\_MULTI\_SZ**\).|  
|**b**|Spécifie que la prochaine valeur est une valeur binaire \(**REG\_BINARY**\).|  
  
## Exemples de syntaxe BNF de  
 Voici quelques exemples de syntaxe pour vous aider à comprendre comment la notation et les littéraux de chaîne s'exécutent dans un script ATL Registrar.  
  
### Exemple 1 de syntaxe  
  
```  
<registry expression> ::= <Add Key>  
```  
  
 spécifie qu' `registry expression` équivaut à `Add Key`.  
  
### Exemple 2 de syntaxe  
  
```  
<registry expression> ::= <Add Key> | <Delete Key>  
```  
  
 spécifie qu' `registry expression` équivaut à `Add Key` ou à `Delete Key`.  
  
### Exemple 3 de syntaxe  
  
```  
<Key Name> ::= '<AlphaNumeric>+'  
```  
  
 spécifie qu' `Key Name` équivaut à un ou plusieurs `AlphaNumerics`.  
  
### Exemple 4 de syntaxe  
  
```  
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name>  
```  
  
 spécifie qu' `Add Key` équivaut à `Key Name`, et que les littéraux de chaîne, `ForceRemove`, `NoRemove`, et `val`, sont facultatifs.  
  
### Exemple 5 de syntaxe  
  
```  
<AlphaNumeric> ::= any character not NULL, that is, ASCII 0  
```  
  
 spécifie qu' `AlphaNumeric` équivaut à tout caractère non null.  
  
### Exemple 6 de syntaxe  
  
```  
val 'testmulti' = m 'String 1\0String 2\0'  
```  
  
 spécifie que le nom de la clé `testmulti` est une valeur à plusieurs chaînes composée d' `String 1` et d' `String 2`.  
  
### Exemple 7 de syntaxe  
  
```  
val 'testhex' = d '&H55'  
```  
  
 spécifie que le nom de la clé `testhex` est une valeur de **DWORD** définie hexadécimal 55 \(85 décimales\).  Notez ce format adhère à la notation de **&H** comme trouvé dans la spécification de Visual Basic.  
  
## Voir aussi  
 [Creating Registrar Scripts](../atl/creating-registrar-scripts.md)