---
title: "L’erreur LNK1256 erreur des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- xml
- LNK1256
dev_langs:
- C++
helpviewer_keywords:
- LNK1256
ms.assetid: 55b64b2b-a56b-436c-a55e-ec9c6dcb050e
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 84964b0a49b236bae056125de8155b18880eb378
ms.openlocfilehash: 02231366d7b20be51e7b918fe7932fc80a38b169
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-error-lnk1256"></a>Erreur des outils Éditeur de liens LNK1256
Échec de l'opération ALINK : raison  
  
 Une des raisons courantes de la survenue de l'erreur LNK1256 est l'existence d'un numéro de version incorrect pour un assembly. La valeur 65 535 n'est pas autorisée, quelle que soit la partie du numéro de version de l'assembly. La plage valide pour les versions d'assembly est comprise entre 0 et 65 534.  
  
 L'erreur LNK1256 peut aussi survenir si ALINK n'a pas trouvé le conteneur de clé nommé. Supprimer le conteneur de clé et l’ajouter à nouveau au CSP de nom fort à l’aide de [Sn.exe (Strong Name Tool)](http://msdn.microsoft.com/Library/c1d2b532-1b8e-4c7a-8ac5-53b801135ec6).  
  
 L'erreur LNK1256 peut aussi être liée à une incompatibilité de version entre l'éditeur de liens et Alink.dll. Une installation endommagée de Visual Studio peut en être la cause. Utilisez **programmes et fonctionnalités** dans le panneau de configuration Windows pour réparer ou réinstaller Visual Studio.  
  
 L'exemple suivant génère l'erreur LNK1256 :  
  
```  
// LNK1256.cpp  
// compile with: /clr /LD  
// LNK1256 expected  
[assembly:System::Reflection::AssemblyVersionAttribute("1.0.65535")];  
public class CMyClass {  
public:  
   int value;  
};  
```
