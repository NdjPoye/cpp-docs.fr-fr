---
title: "Mots cl&#233;s contextuels  (extensions de composant C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "internal_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mots clés contextuels"
ms.assetid: e33da089-f434-44e9-8cce-4668d05a8939
caps.latest.revision: 19
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Mots cl&#233;s contextuels  (extensions de composant C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les *mots clés contextuels* sont des éléments de langage reconnus uniquement dans des contextes spécifiques.  En dehors du contexte spécifique, un mot clé contextuel peut être un symbole défini par l'utilisateur.  
  
## Tous les runtimes  
 **Notes**  
  
 Voici une liste de mots clés contextuels :  
  
-   [abstract](../windows/abstract-cpp-component-extensions.md)  
  
-   [délégué](../windows/delegate-cpp-component-extensions.md)  
  
-   [événement](../windows/event-cpp-component-extensions.md)  
  
-   [finally](../dotnet/finally.md)  
  
-   [for each, in](../dotnet/for-each-in.md)  
  
-   [initonly](../dotnet/initonly-cpp-cli.md)  
  
-   `internal` \(voir [Visibilité de membre](../misc/member-visibility.md)\)  
  
-   [literal](../windows/literal-cpp-component-extensions.md)  
  
-   [override](../windows/override-cpp-component-extensions.md)  
  
-   [property](../windows/property-cpp-component-extensions.md)  
  
-   [sealed](../windows/sealed-cpp-component-extensions.md)  
  
-   `where` \(partie de [Generics](../windows/generics-cpp-component-extensions.md)\)  
  
 Pour des raisons de lisibilité, vous pouvez limiter votre utilisation des mots clés contextuels comme symboles définis par l'utilisateur.  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **Notes**  
  
 \(Il n'existe aucune note spécifique à la plateforme pour cette fonctionnalité.\)  
  
### Conditions requises  
 Option du compilateur : **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Notes**  
  
 \(Il n'existe aucune note spécifique à la plateforme pour cette fonctionnalité.\)  
  
### Conditions requises  
 Option du compilateur : **\/clr**  
  
### Exemples  
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
  
  **100**   
## Voir aussi  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)