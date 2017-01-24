---
title: "Comment&#160;: diagnostiquer et r&#233;soudre les probl&#232;mes de compatibilit&#233; de l&#39;assembly (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "compatibilité, entre les assemblys"
  - "exceptions, diagnostiquer un comportement étrange"
  - "contrôle de version"
  - "contrôle de version, diagnostiquer les conflits"
ms.assetid: 297c71e3-04a8-4d24-a5dc-b04a2c5cc6fb
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: diagnostiquer et r&#233;soudre les probl&#232;mes de compatibilit&#233; de l&#39;assembly (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique explique ce qui peut se passer lorsque la version d'un assembly référencée à la compilation ne correspond pas à la version de l'assembly référencée à l'exécution, et comment éviter ce problème.  
  
 Lorsqu'un assembly est compilé, d'autres assemblys peuvent être référencés à l'aide de la syntaxe `#using`.  Au cours de la compilation, le compilateur accède à ces assemblys.  Les informations fournies par ces assemblys servent à prendre des décisions d'optimisation.  
  
 Toutefois, si l'assembly référencé est modifié et recompilé, et si vous ne recompilez pas l'assembly référenceur qui en dépend, les assemblys risquent de ne toujours pas être compatibles.  Les décisions d'optimisation qui étaient jusqu'ici valides peuvent ne plus être correctes avec la nouvelle version de l'assembly.  Diverses erreurs d'exécution peuvent se produire en raison de ces incompatibilités.  Aucune exception spécifique ne sera produite dans de tels cas.  La façon dont la défaillance est rapportée à l'exécution dépend de la nature de la modification du code qui a provoqué le problème.  
  
 Ces erreurs ne doivent pas poser problème dans votre code final de production tant que l'application entière est reconstituée pour la version finale de votre produit.  Les assemblys diffusés au public doivent être marqués d'un numéro de version officiel, ce qui évitera l'apparition de ces problèmes.  Pour plus d'informations, consultez [Versioning des assemblys](../Topic/Assembly%20Versioning.md).  
  
### Diagnostic et résolution d'une erreur d'incompatibilité  
  
1.  Si vous découvrez des exceptions d'exécution ou d'autres situations d'erreur dans le code qui référence un autre assembly, sans pouvoir en identifier la cause, vous avez peut\-être affaire à un assembly obsolète.  
  
2.  Commencez par isoler et reproduire l'exception ou la situation d'erreur.  Un problème causé par une exception obsolète doit être reproductible.  
  
3.  Vérifiez l'horodatage de tous les assemblys référencés dans votre application.  
  
4.  Si les horodatages de tous les assemblys référencés montrent un retard par rapport à l'horodatage de la dernière compilation de votre application, c'est que votre application est obsolète.  Dans ce cas, recompilez votre application avec l'assembly le plus récent et procédez aux modifications de code nécessaires.  
  
5.  Relancez l'application, exécutez les étapes qui reproduisent le problème et vérifiez que l'exception ne se produit pas.  
  
## Exemple  
 Le programme suivant illustre le problème en réduisant l'accessibilité d'une méthode et en tentant d'accéder à cette méthode dans un autre assembly sans recompiler.  Essayez tout d'abord de compiler `changeaccess.cpp`.  Il s'agit de l'assembly référencé qui sera modifié.  Compilez ensuite `referencing.cpp`.  La compilation réussit.  Maintenant, réduisez l'accessibilité de la méthode appelée.  Recompilez `changeaccess.cpp` avec l'indicateur `/DCHANGE_ACCESS`.  Cette procédure fait de la méthode une méthode protégée, plutôt que privée, de façon à ce qu'elle puisse être appelée plus longtemps légalement.  Sans recompiler `referencing.exe`, relancez l'application.  Une exception <xref:System.MethodAccessException> se produira.  
  
```  
// changeaccess.cpp  
// compile with: /clr:safe /LD  
// After the initial compilation, add /DCHANGE_ACCESS and rerun  
// referencing.exe to introduce an error at runtime. To correct  
// the problem, recompile referencing.exe  
  
public ref class Test {  
#if defined(CHANGE_ACCESS)  
protected:  
#else  
public:  
#endif  
  
  int access_me() {  
    return 0;  
  }  
  
};  
  
```  
  
```  
// referencing.cpp  
// compile with: /clr:safe   
#using <changeaccess.dll>  
  
// Force the function to be inline, to override the compiler's own  
// algorithm.  
__forceinline  
int CallMethod(Test^ t) {  
  // The call is allowed only if access_me is declared public  
  return t->access_me();  
}  
  
int main() {  
  Test^ t = gcnew Test();  
  try  
  {  
    CallMethod(t);  
    System::Console::WriteLine("No exception.");  
  }  
  catch (System::Exception ^ e)  
  {  
    System::Console::WriteLine("Exception!");  
  }  
  return 0;  
}  
  
```  
  
## Voir aussi  
 [\#using, directive](../preprocessor/hash-using-directive-cpp.md)   
 [Types managés](../dotnet/managed-types-cpp-cli.md)