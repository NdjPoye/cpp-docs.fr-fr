---
title: "Understanding Parse Trees | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "parse trees"
ms.assetid: 668ce2dd-a1c3-4ca0-8135-b25267cb6a85
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Understanding Parse Trees
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez définir un ou plusieurs analysez les arborescences dans votre script d'inscription, où chaque analysez l'arborescence a la forme suivante :  
  
```  
<root key>{<registry expression>}+  
```  
  
 où :  
  
```  
<root key> ::=  HKEY_CLASSES_ROOT | HKEY_CURRENT_USER |  
               HKEY_LOCAL_MACHINE | HKEY_USERS |  
               HKEY_PERFORMANCE_DATA | HKEY_DYN_DATA |  
               HKEY_CURRENT_CONFIG | HKCR | HKCU |  
               HKLM | HKU | HKPD | HKDD | HKCC  
<registry expression> ::= <Add Key> | <Delete Key>  
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name>  
              [<Key Value>][{< Add Key>}]  
<Delete Key> ::=  Delete<Key Name>  
<Key Name> ::= '<AlphaNumeric>+'  
<AlphaNumeric> ::= any character not NULL, i.e. ASCII 0  
<Key Value> ::== <Key Type><Key Name>  
<Key Type> ::= s | d  
<Key Value> ::= '<AlphaNumeric>'  
```  
  
> [!NOTE]
>  `HKEY_CLASSES_ROOT` et `HKCR` sont équivalents ; `HKEY_CURRENT_USER` et `HKCU` sont équivalents ; et ainsi de suite.  
  
 Une arborescence d'analyser peut ajouter plusieurs clés et sous\-clés à \<root key\>.  Ce faisant, elle stocke le handle d'une sous\-clé ouvert jusqu'à ce que l'analyseur a terminé analyser toutes ses sous\-clés.  Cette approche est plus efficace que l'opération sur une clé à la fois, comme nous l'avons vu dans l'exemple suivant :  
  
```  
HKEY_CLASSES_ROOT  
{  
   'MyVeryOwnKey'  
   {  
      'HasASubKey'  
      {  
         'PrettyCool?'  
      }  
   }  
}  
```  
  
 Ici, le registre affiche initialement \(le\) crée `HKEY_CLASSES_ROOT\MyVeryOwnKey`.  Il voit tandis que `MyVeryOwnKey` a une sous\-clé.  Plutôt que fermez la clé à `MyVeryOwnKey`, le registre conserve le handle et ouvre \(le\) crée `HasASubKey` à l'aide de ce handle parent.  \(La base de registres peut être plus lente lorsqu'un handle parent n'est ouvert.\) Ainsi, ouvrir `HKEY_CLASSES_ROOT\MyVeryOwnKey` puis ouvrir `HasASubKey` avec `MyVeryOwnKey` en tant que parent est plus rapide que l'ouverture `MyVeryOwnKey`, `MyVeryOwnKey`fermeture, puis ouvrir `MyVeryOwnKey\HasASubKey`.  
  
## Voir aussi  
 [Creating Registrar Scripts](../atl/creating-registrar-scripts.md)