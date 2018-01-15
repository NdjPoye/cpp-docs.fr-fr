---
title: "ATL (inscription) et les arborescences d’analyse | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: parse trees
ms.assetid: 668ce2dd-a1c3-4ca0-8135-b25267cb6a85
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c8ce648a541f6e0e2d4fac2e6ee19226e41f20ad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="understanding-parse-trees"></a>Présentation des arborescences d’analyse
Vous pouvez définir une ou plusieurs arborescences d’analyse dans votre script registrar où chaque arborescence d’analyse a la forme suivante :  
  
```  
<root key>{<registry expression>}+  
```  
  
 où :  
  
```  
<root key> ::= HKEY_CLASSES_ROOT | HKEY_CURRENT_USER |  
    HKEY_LOCAL_MACHINE | HKEY_USERS |  
    HKEY_PERFORMANCE_DATA | HKEY_DYN_DATA |  
    HKEY_CURRENT_CONFIG | HKCR | HKCU |  
    HKLM | HKU | HKPD | HKDD | HKCC  
<registry expression> ::= <Add Key> | <Delete Key>  
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name>  
 [<Key Value>][{<Add Key>}]  
<Delete Key> ::= Delete<Key Name>  
<Key Name> ::= '<AlphaNumeric>+'  
<AlphaNumeric> ::= any character not NULL, i.e. ASCII 0  
<Key Value> ::== <Key Type><Key Name>  
<Key Type> ::= s | d  
<Key Value> ::= '<AlphaNumeric>'  
```  
  
> [!NOTE]
> `HKEY_CLASSES_ROOT`et `HKCR` sont équivalentes ; `HKEY_CURRENT_USER` et `HKCU` sont équivalents ; et ainsi de suite.  
  
 Une arborescence d’analyse peut ajouter plusieurs clés et des sous-clés pour la \<clé racine >. Ce faisant, il conserve un handle de sous-clé ouvert jusqu'à ce que l’analyseur a terminé l’analyse de toutes ses sous-clés. Cette approche est plus efficace que le traitement d’une clé unique à la fois, comme illustré dans l’exemple suivant :  
  
```  
HKEY_CLASSES_ROOT  
{  
 'MyVeryOwnKey'  
 {  
 'HasASubKey'  
 {  
 'PrettyCool'  
 }  
 }  
}  
```  
  
 Ici, le bureau d’enregistrement s’affiche initialement (crée) `HKEY_CLASSES_ROOT\MyVeryOwnKey`. Elle constate que `MyVeryOwnKey` a une sous-clé. Plutôt que la fermeture de la clé à `MyVeryOwnKey`, le bureau d’enregistrement conserve le handle et ouvre (crée) `HasASubKey` à l’aide de ce handle parent. (Le Registre système peut être plus lent quand aucun handle parent n’est ouvert.) Par conséquent, ouverture `HKEY_CLASSES_ROOT\MyVeryOwnKey` , puis en ouvrant `HasASubKey` avec `MyVeryOwnKey` comme parent est plus rapide que lors de l’ouverture `MyVeryOwnKey`, fermeture `MyVeryOwnKey`, puis en ouvrant `MyVeryOwnKey\HasASubKey`.  
  
## <a name="see-also"></a>Voir aussi  
 [Création de scripts d’inscription](../atl/creating-registrar-scripts.md)

