---
title: naked (C++) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- naked_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], naked
- naked __declspec keyword
ms.assetid: 69723241-05e1-439b-868e-20a83a16ab6d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 84e172c24bbb87f9243a4c0de25a98c90e043acc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="naked-c"></a>naked (C++)
**Section spécifique à Microsoft**  
  
 Pour les fonctions déclarées avec le `naked` attribut, le compilateur génère du code sans code de prologue et épilogue. Vous pouvez utiliser cette fonctionnalité pour écrire vos propres séquences de code de prologue/épilogue à l'aide de code assembleur inline. Les fonctions naked sont particulièrement utiles pour l'écriture de pilotes de périphériques virtuels.  Notez que la `naked` attribut est valide uniquement sur x86 et ARM et n’est pas disponible sur [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```  
__declspec(naked) declarator  
```  
  
## <a name="remarks"></a>Notes  
 Étant donné que la `naked` attribut se rapporte uniquement à la définition d’une fonction et n’est pas un modificateur de type, les fonctions naked doivent utiliser la syntaxe à attributs étendus et le [__declspec](../cpp/declspec.md) (mot clé).  
  

 Le compilateur ne peut pas générer une fonction inline pour une fonction marquée avec l’attribut naked, même si la fonction est également marquée avec la [__forceinline](inline-functions-cpp.md) (mot clé).  

  
 Le compilateur émet une erreur si le `naked` attribut est appliqué à une autre que la définition d’une méthode membre non.  
  
## <a name="examples"></a>Exemples  
 Ce code définit une fonction avec la `naked` attribut :  
  
```  
__declspec( naked ) int func( formal_parameters ) {}  
```  
  
 Ou, vous pouvez également :  
  
```  
#define Naked __declspec( naked )  
Naked int func( formal_parameters ) {}  
```  
  
 L'attribut `naked` affecte uniquement la nature de la génération de code du compilateur pour les séquences de prologue et d'épilogue de la fonction. Il n'affecte pas le code généré pour appeler de telles fonctions. Ainsi, l'attribut `naked` n'est pas considéré comme faisant partie du type de la fonction, et les pointeurs fonction ne peuvent pas avoir l'attribut `naked`. De plus, l'attribut `naked` ne peut pas être appliqué à une définition de données. Par exemple, cet exemple de code génère une erreur :  
  
```  
__declspec( naked ) int i;       // Error--naked attribute not  
                                 // permitted on data declarations.  
```  
  
 L'attribut `naked` se rapporte uniquement à la définition de la fonction et ne peut pas être spécifié dans le prototype de la fonction. Par exemple, cette déclaration génère une erreur du compilateur :  
  
```  
__declspec( naked ) int func();  // Error--naked attribute not   
                                 // permitted on function declarations  
```  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [__declspec](../cpp/declspec.md)   
 [Mots clés](../cpp/keywords-cpp.md)   
 [Appels de fonction naked](../cpp/naked-function-calls.md)