---
title: "Mots clés contextuels (Extensions du composant C++) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: internal_CPP
dev_langs: C++
helpviewer_keywords: context-sensitive keywords
ms.assetid: e33da089-f434-44e9-8cce-4668d05a8939
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1d5af53c04c6ff9ec28e7b83cd3a8f9bce8307c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="context-sensitive-keywords--c-component-extensions"></a>Mots clés contextuels  (extensions de composant C++)
*Mots clés contextuels* sont des éléments de langage reconnus uniquement dans des contextes spécifiques. En dehors du contexte spécifique, un mot clé contextuel peut être un symbole défini par l'utilisateur.  
  
## <a name="all-runtimes"></a>Tous les runtimes  
 **Remarques**  
  
 Voici une liste de mots clés contextuels :  
  
-   [abstract](../windows/abstract-cpp-component-extensions.md)  
  
-   [delegate](../windows/delegate-cpp-component-extensions.md)  
  
-   [event](../windows/event-cpp-component-extensions.md)  
  
-   [finally](../dotnet/finally.md)  
  
-   [for each, in](../dotnet/for-each-in.md)  
  
-   [initonly](../dotnet/initonly-cpp-cli.md)  
  
-   `internal`   
  
-   [littéral](../windows/literal-cpp-component-extensions.md)  
  
-   [override](../windows/override-cpp-component-extensions.md)  
  
-   [propriété](../windows/property-cpp-component-extensions.md)  
  
-   [sealed](../windows/sealed-cpp-component-extensions.md)  
  
-   `where`(dans le cadre du [génériques](../windows/generics-cpp-component-extensions.md))  
  
 Pour des raisons de lisibilité, vous voudrez limiter votre utilisation des mots clés contextuels comme symboles définis par l’utilisateur.  
  
## <a name="windows-runtime"></a>Windows Runtime  
 **Remarques**  
  
 (Il n’existe aucune note spécifique à la plateforme pour cette fonctionnalité.)  
  
### <a name="requirements"></a>Configuration requise  
 Option du compilateur : **/ZW**  
  
## <a name="common-language-runtime"></a>Common Language Runtime 
 **Remarques**  
  
 (Il n’existe aucune note spécifique à la plateforme pour cette fonctionnalité.)  
  
### <a name="requirements"></a>Configuration requise  
 Option du compilateur : **/clr**  
  
### <a name="examples"></a>Exemples  
 **Exemple**  
  
 L'exemple de code suivant montre que dans le contexte approprié, le mot clé contextuel `property` peut être utilisé pour définir une propriété et une variable.  
  
```  
// context_sensitive_keywords.cpp  
// compile with: /clr  
public ref class C {  
   int MyInt;  
public:  
   C() : MyInt(99) {}  
  
   property int Property_Block {   // context-sensitive keyword  
      int get() { return MyInt; }  
   }  
};  
  
int main() {  
   int property = 0;               // variable name  
   C ^ MyC = gcnew C();  
   property = MyC->Property_Block;  
   System::Console::WriteLine(++property);  
}  
```  
  
 **Sortie**  
  
```Output  
100  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Extensions de composant pour les plateformes Runtime](../windows/component-extensions-for-runtime-platforms.md)