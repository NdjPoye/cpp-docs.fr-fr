---
title: detect_mismatch | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-pragma.detect_mismatch
- detect_mismatch_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, detect_mismatch
- detect_mismatch pragma
ms.assetid: ddb13ac9-0e2f-40ce-be69-7e44c04f5a12
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 875b6980a3c55c07b5765d6d0fc12be1796ee3a3
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="detectmismatch"></a>detect_mismatch
Place un enregistrement dans un objet. L'éditeur de liens vérifie les éventuelles incompatibilités entre ces enregistrements.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
#pragma detect_mismatch( "name", "value"))  
```  
  
## <a name="remarks"></a>Notes  
 Lorsque vous liez le projet, l'éditeur de liens génère une erreur `LNK2038` si le projet contient deux objets qui ont le même `name` mais qui ont chacun une `value` différente. Utilisez ce pragma pour empêcher la liaison des fichiers objets incohérents.  
  
 Le nom et la valeur sont des littéraux de chaîne qui obéissent aux règles des littéraux de chaîne en ce qui concerne les caractères d'échappement et la concaténation. Ils respectent la casse et ne peuvent pas contenir de virgule, de signe égal, de guillemets ou de caractère `null`.  
  
## <a name="example"></a>Exemple  
 Cet exemple crée deux fichiers qui ont des numéros de version différents pour la même étiquette de version.  
  
```  
// pragma_directive_detect_mismatch_a.cpp  
#pragma detect_mismatch("myLib_version", "9")  
int main ()  
{  
   return 0;  
}  
  
// pragma_directive_detect_mismatch_b.cpp  
#pragma detect_mismatch("myLib_version", "1")  
```  
  
 Si vous compilez ces deux fichiers à l'aide de la ligne de commande `cl pragma_directive_detect_mismatch_a.cpp pragma_directive_detect_mismatch_b.cpp`, vous recevez l'erreur `LNK2038`.  
  
## <a name="see-also"></a>Voir aussi  
 [Directives pragma et mot clé _Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)