---
title: "__try_cast | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__try_cast"
  - "__try_cast_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__try_cast (mot clé)"
  - "échecs de cast"
  - "exceptions, opérations cast infructueuses"
  - "lever des exceptions, opérations cast infructueuses"
ms.assetid: e9e5da3a-f5b9-4915-b30a-a432e8574d03
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# __try_cast
**Remarque** Cette rubrique s'applique uniquement à la version 1 des extensions managées pour C\+\+. Cette syntaxe doit être utilisée uniquement pour conserver le code de la version 1. Consultez [safe\_cast](../windows/safe-cast-cpp-component-extensions.md) Pour plus d’informations sur l’utilisation de la fonctionnalité équivalente dans la nouvelle syntaxe.  
  
 Exécute le cast spécifié ou lève une exception si le cast échoue.  
  
## Syntaxe  
  
```  
  
__try_cast <  
 type-id  
 >  
(  
expression   
)  
  
```  
  
## Notes  
 Le mot clé `__try_cast` \(dont le comportement est semblable à celui de [dynamic\_cast](../cpp/dynamic-cast-operator.md)\) permet de lever automatiquement une exception \(de type **System::InvalidCastException**\) dès lors que l'opération de cast spécifiée échoue.  
  
 Le mot clé `__try_cast` peut être utilisé pendant la phase de test de votre application pour vous alerter automatiquement en cas de risque d'échec de cast.  
  
 Lorsque les Extensions managées pour C\+\+, remplacez `__try_cast` appelle avec [safe\_cast](../windows/safe-cast-cpp-component-extensions.md).  
  
 `__try_cast` ne fonctionne pas sur les casts du type pointeur à valeur \([\_\_value](../misc/value.md)\), car il n'est pas possible de vérifier les types au moment de l'exécution.  
  
## Exemple  
 Dans l'exemple suivant, une tentative de cast d'un pointeur \(de type `Derived`\) en un autre pointeur \(de type `MoreDerived` \) est effectuée. Si le cast échoue, il est intercepté et signalé par le bloc catch :  
  
```  
// keyword__try_cast.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
__gc struct Base {};   
__gc struct Derived : Base {};  
__gc struct MoreDerived : Derived {};  
  
int main() {  
   Base*bp = new Derived;  
   try {  
       MoreDerived* mdp = __try_cast<MoreDerived*>(bp);  
   }  
   catch(System::InvalidCastException*) {  
       Console::WriteLine("Could not cast 'bp' to MoreDerived*");  
   }  
}  
```  
  
## Sortie  
  
```  
Could not cast 'bp' to MoreDerived*  
```