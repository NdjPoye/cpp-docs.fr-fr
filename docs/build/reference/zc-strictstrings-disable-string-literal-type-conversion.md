---
title: "/Zc:strictStrings (D&#233;sactiver la conversion du type de litt&#233;ral de cha&#238;ne) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/Zc:strictStrings"
  - "strictStrings"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc (options du compilateur C++)"
  - "/Zc:strictStrings"
  - "strictStrings"
  - "Zc (options du compilateur C++)"
  - "-Zc (options du compilateur C++)"
ms.assetid: b7eb3f3b-82c1-48a2-8e63-66bad7397b46
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /Zc:strictStrings (D&#233;sactiver la conversion du type de litt&#233;ral de cha&#238;ne)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Quand il est spécifié, le compilateur requiert une conformité de qualification `const` stricte pour les pointeurs initialisés à l'aide de littéraux de chaîne.  
  
## Syntaxe  
  
```  
/Zc:strictStrings[-]  
```  
  
## Notes  
 Si **\/Zc:strictStrings** est spécifié, le compilateur applique les qualifications `const` C\+\+ standard pour les littéraux de chaîne, en tant que type 'tableau de `const` `char`' ou 'tableau de `const` `wchar_t`', en fonction de la déclaration.  Les littéraux de chaîne sont immuables et une tentative de modification du contenu d'un de ces littéraux entraîne une erreur de violation d'accès au moment de l'exécution.  Vous devez déclarer un pointeur de chaîne en tant que `const` pour l'initialiser en utilisant un littéral de chaîne ou utilisez un `const_cast` explicite pour initialiser un pointeur non `const`.  Par défaut, ou si **\/Zc:strictStrings\-** est spécifié, le compilateur n'applique pas les qualifications `const` C\+\+ standard pour les pointeurs de chaîne initialisés à l'aide de littéraux de chaîne.  
  
 Utilisez l'option **\/Zc:strictStrings** pour empêcher la compilation de code incorrect.  Cet exemple montre comment une simple erreur de déclaration conduit à un incident au moment de l'exécution :  
  
```cpp  
// strictStrings_off.cpp  
// compile by using: cl /W4 strictStrings_off.cpp  
int main() {  
   wchar_t* str = L"hello";  
   str[2] = L'a'; // run-time error: access violation  
}  
```  
  
 Quand **\/Zc:strictStrings** est activé, le même code signale une erreur dans la déclaration de `str`.  
  
```cpp  
// strictStrings_on.cpp  
// compile by using: cl /Zc:strictStrings /W4 strictStrings_on.cpp  
int main() {  
   wchar_t* str = L"hello"; // error: Conversion from string literal   
   // loses const qualifier  
   str[2] = L'a';   
}  
```  
  
 Si vous utilisez `auto` pour déclarer un pointeur de chaîne, le compilateur crée automatiquement la déclaration de type de pointeur `const` correcte.  Une tentative de modification du contenu d'un pointeur `const` est signalée par le compilateur en tant qu'erreur.  
  
> [!NOTE]
>  La bibliothèque C\+\+ standard dans [!INCLUDE[cpp_dev12_long](../../build/reference/includes/cpp_dev12_long_md.md)] ne prend pas en charge l'option de compilateur **\/Zc:strictStrings** dans les versions Debug.  Si vous voyez plusieurs erreurs [C2665](../../error-messages/compiler-errors-2/compiler-error-c2665.md) dans votre sortie de build, elles sont peut\-être dues à cela.  
  
 Pour plus d'informations sur les problèmes de conformité dans Visual C\+\+, consultez [Comportement non standard](../../cpp/nonstandard-behavior.md).  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, voir [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Sélectionnez le dossier **C\/C\+\+**.  
  
3.  Sélectionnez la page de propriétés **Ligne de commande**.  
  
4.  Modifiez la propriété **Options supplémentaires** pour inclure `/Zc:strictStrings`, puis choisissez **OK**.  
  
## Voir aussi  
 [\/Zc \(Conformité\)](../../build/reference/zc-conformance.md)