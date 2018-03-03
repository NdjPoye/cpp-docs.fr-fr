---
title: "Erreur LNK1256 des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bbbb14e4f4fdef63b58bdef5ecafcfe0b045f412
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1256"></a>Erreur des outils Éditeur de liens LNK1256
Échec de l'opération ALINK : raison  
  
 Une des raisons courantes de la survenue de l'erreur LNK1256 est l'existence d'un numéro de version incorrect pour un assembly. La valeur 65 535 n'est pas autorisée, quelle que soit la partie du numéro de version de l'assembly. La plage valide pour les versions d’assembly est 0 - 65534.  
  
 L'erreur LNK1256 peut aussi survenir si ALINK n'a pas trouvé le conteneur de clé nommé. Supprimer le conteneur de clé et l’ajouter à nouveau pour le fournisseur de services cryptographiques de nom fort à l’aide de [Sn.exe (Strong Name Tool)](/dotnet/framework/tools/sn-exe-strong-name-tool).  
  
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