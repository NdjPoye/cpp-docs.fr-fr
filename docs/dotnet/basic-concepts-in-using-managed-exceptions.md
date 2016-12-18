---
title: "Concepts de base dans l&#39;utilisation des exceptions manag&#233;es | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "__finally (mot clé), exceptions managées"
  - "catch (blocs)"
  - "exceptions, managé"
  - "lever des exceptions, exceptions managées"
  - "try-catch (gestion des exceptions)"
  - "try-catch (gestion des exceptions), applications managées"
  - "Visual C++, gérer les exceptions managées"
ms.assetid: 40ce8931-1ecc-491a-815f-733b23fcba35
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Concepts de base dans l&#39;utilisation des exceptions manag&#233;es
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique traite de la gestion des exceptions dans les applications managées.  Autrement dit, une application qui est compilée avec l'option **\/clr** du compilateur.  
  
## Dans cette rubrique  
  
-   [Lever des exceptions dans \/clr](#vcconbasicconceptsinusingmanagedexceptionsanchor1)  
  
-   [Blocs try\/catch des extensions CLR](#vcconbasicconceptsinusingmanagedexceptionsanchor2)  
  
## Remarques  
 Si vous compilez avec l'option **\/clr**, vous pouvez gérer les exceptions CLR ainsi que la [Gestion des exceptions C\+\+](../cpp/cpp-exception-handling.md) standard et [gestion des exceptions structurée](../cpp/structured-exception-handling-c-cpp.md) \(SEH\).  Une exception CLR est toute exception levée par un type managé.  La classe [System::Exception](https://msdn.microsoft.com/en-us/library/system.exception.aspx) fournit de nombreuses méthodes utiles pour le traitement des exceptions CLR et est recommandée en tant que classe de base pour les classes d'exception définies par l'utilisateur.  
  
 Capter des types d'exception dérivés d'une interface n'est pas pris en charge par **\/clr**.  En outre, le CLR ne vous permet pas d'intercepter les exceptions de dépassement de capacité de la pile ; une exception de dépassement de capacité de la pile mettra fin au processus.  
  
 Pour plus d'informations sur les différences de gestion des exceptions dans les applications managées et non managées, consultez [Différences de comportement de gestion des exceptions dans les extensions managées pour C\+\+](../dotnet/differences-in-exception-handling-behavior-under-clr.md).  
  
##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor1"></a> Lever des exceptions dans \/clr  
 Le lancer d'expression C\+\+ est étendu pour générer un handle à un type CLR.  L'exemple suivant crée un type d'exception personnalisé puis génère une instance de ce type :  
  
```  
// clr_exception_handling.cpp  
// compile with: /clr /c  
ref struct MyStruct: public System::Exception {  
public:  
   int i;  
};  
  
void GlobalFunction() {  
   MyStruct^ pMyStruct = gcnew MyStruct;  
   throw pMyStruct;  
}  
```  
  
 Un type de valeur doit être encapsulé avant d'être levé :  
  
```  
// clr_exception_handling_2.cpp  
// compile with: /clr /c  
value struct MyValueStruct {  
   int i;  
};  
  
void GlobalFunction() {  
   MyValueStruct v = {11};  
   throw (MyValueStruct ^)v;  
}  
```  
  
##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor2"></a> Blocs try\/catch des extensions CLR  
 La même structure de bloc **try**\/**catch** peut être utilisée pour intercepter le CLR et les exceptions natives :  
  
```  
// clr_exception_handling_3.cpp  
// compile with: /clr  
using namespace System;  
ref struct MyStruct : public Exception {  
public:  
   int i;  
};  
  
struct CMyClass {  
public:  
   double d;  
};  
  
void GlobalFunction() {  
   MyStruct^ pMyStruct = gcnew MyStruct;  
   pMyStruct->i = 11;  
   throw pMyStruct;  
}  
  
void GlobalFunction2() {  
   CMyClass c = {2.0};  
   throw c;  
}  
  
int main() {  
   for ( int i = 1; i >= 0; --i ) {  
      try {  
         if ( i == 1 )  
            GlobalFunction2();  
         if ( i == 0 )  
            GlobalFunction();  
      }  
      catch ( CMyClass& catchC ) {  
         Console::WriteLine( "In 'catch(CMyClass& catchC)'" );  
         Console::WriteLine( catchC.d );  
      }  
      catch ( MyStruct^ catchException ) {  
         Console::WriteLine( "In 'catch(MyStruct^ catchException)'" );  
         Console::WriteLine( catchException->i );  
      }  
   }  
}  
```  
  
### Sortie  
  
```  
In 'catch(CMyClass& catchC)'  
2  
In 'catch(MyStruct^ catchException)'  
11  
```  
  
### Commande pour dérouler des objets C\+\+  
 Le déroulement se produit pour tous les objets C\+\+ avec les destructeurs qui peuvent être sur la pile d'exécution entre la fonction levée et la fonction de gestion.  Puisque les types CLR sont alloués sur le tas, le déroulement ne s'applique pas à ceux\-ci.  
  
 L'ordre des événements pour une exception levée est la suivante :  
  
1.  L'exécution parcourt la pile et recherche la clause catch appropriée, ou en cas de SEH, un filtre pour SEH, pour intercepter l'exception.  Les clauses catch sot cherchées en premier dans l'ordre lexical, puis dynamiquement en parcourant la pile des appels.  
  
2.  Une fois que le gestionnaire correct est trouvé, la pile est déroulée jusqu'à ce point.  Pour chaque appel de fonction dans la pile, ses objets locaux sont détruits et les blocs \_\_finally sont exécutés, en partant du plus imbriqué.  
  
3.  Une fois la pile est déroulée, la clause CATCH est exécutée.  
  
### Capter les types non pris en charge  
 Lorsqu'un type d'objet non managé est levé, il est inclus avec une exception de type [System::Runtime.InteropServices::SEHException](https://msdn.microsoft.com/en-us/library/system.runtime.interopservices.sehexception.aspx).  En recherchant la clause **catch** appropriée, il existe deux possibilités.  
  
-   Si un type C\+\+ natif est produit, l'exception est déroulée et comparée au type rencontré.  Cette comparaison autorise un type natif C\+\+ à être intercepté de la façon régulière.  
  
-   Toutefois, si une clause **catch** de type **SEHException** ou de ses classes de base est examinée d'abord, la clause interceptera l'exception.  Par conséquent, vous devez placer toutes les clauses qui interceptent des types C\+\+ natifs avant toute clause catch de types CLR.  
  
 Prenez note de ce qui suit :  
  
```  
catch(Object^)  
```  
  
 et  
  
```  
catch(...)  
```  
  
 les deux intercepteront n'importe quel type y compris des exceptions SEH.  
  
 Si un type managé est intercepté par catch\(Object^\), cela ne détruira pas l'objet levé.  
  
 En levant ou en interceptant les exceptions non gérées, nous vous recommandons d'utiliser l'option du compilateur [\/EHsc](../build/reference/eh-exception-handling-model.md) au lieu de **\/EHs** ou de **\/EHa**.  
  
## Voir aussi  
 [Exception Handling](../windows/exception-handling-cpp-component-extensions.md)   
 [safe\_cast](../windows/safe-cast-cpp-component-extensions.md)   
 [Gestion des exceptions](../cpp/exception-handling-in-visual-cpp.md)