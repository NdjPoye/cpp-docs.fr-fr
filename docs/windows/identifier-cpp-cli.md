---
title: "__identifier (C++/CLI) | Microsoft Docs"
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
  - "__identifier"
  - "__identifier_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__identifier keyword [C++]"
ms.assetid: 348428af-afa7-4ff3-b571-acf874301cf2
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __identifier (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Permet d'utiliser des mots clés Visual C\+\+ comme identificateurs.  
  
## Toutes les plateformes  
 **Syntaxe**  
  
```  
  
__identifier(  
Visual_C++_keyword  
)  
  
```  
  
 **Remarques**  
  
 L'utilisation du mot clé `__identifier` des identificateurs qui ne sont pas des mots clés est autorisée, mais fortement déconseillée en question de style.  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
  
### Conditions requises  
 Option du compilateur : **\/ZW**  
  
### Exemples  
 **Exemple**  
  
 Dans l'exemple suivant, une classe nommée `template` est créée en c et distribuées en tant que DLL.  Dans le programme Visual C\+\+ qui utilise la classe `template`, le mot clé `__identifier` cache le fait que `template` est un mot clé de langage C\+\+.  
  
```  
// identifier_template.cs  
// compile with: /target:library  
public class template {  
   public void Run() { }  
}  
```  
  
```  
// keyword__identifier.cpp  
// compile with: /ZW  
#using <identifier_template.dll>  
int main() {  
   __identifier(template)^ pTemplate = ref new __identifier(template)();  
   pTemplate->Run();  
}  
```  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Remarques**  
  
 Le mot clé `__identifier` est valide avec les options du compilateur **\/clr** et **\/clr:oldSyntax**.  
  
### Conditions requises  
 Option du compilateur : **\/clr**  
  
### Exemples  
 **Exemple**  
  
 Dans l'exemple suivant, une classe nommée `template` est créée en c et distribuées en tant que DLL.  Dans le programme Visual C\+\+ qui utilise la classe `template`, le mot clé `__identifier` cache le fait que `template` est un mot clé de langage C\+\+.  
  
```  
// identifier_template.cs  
// compile with: /target:library  
public class template {  
   public void Run() { }  
}  
```  
  
```  
// keyword__identifier.cpp  
// compile with: /clr  
#using <identifier_template.dll>  
  
int main() {  
   __identifier(template) ^pTemplate = gcnew __identifier(template)();  
   pTemplate->Run();  
}  
```  
  
## Voir aussi  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)   
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)