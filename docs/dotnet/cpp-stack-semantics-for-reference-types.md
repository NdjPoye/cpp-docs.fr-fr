---
title: "S&#233;mantique de pile C++ pour les types de r&#233;f&#233;rence | Microsoft Docs"
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
  - "types référence, C++ (sémantique de pile)"
ms.assetid: 319a1304-f4a4-4079-8b84-01cec847d531
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# S&#233;mantique de pile C++ pour les types de r&#233;f&#233;rence
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Avant Visual C\+\+ 2005, une instance d'un type de référence pouvait être créée à l'aide de l'opérateur d' `new`, qui a créé l'objet sur le segment récupéré par le garbage collector.  Toutefois, vous pouvez à présent créer une instance d'un type de référence en utilisant la même syntaxe que vous devriez utiliser pour créer une instance d'un type natif dans la pile.  Par conséquent, vous n'avez pas besoin d'utiliser [ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md) pour créer un objet de type référence.  Et lorsque l'objet est hors de portée, le compilateur appelle le destructeur de l'objet.  
  
## Remarques  
 Lorsque vous créez une instance d'un type de référence à l'aide de la sémantique de pile, le compilateur crée en interne l'instance sur le segment récupéré par le garbage collector \(utilisant `gcnew`\).  
  
 Lorsque la signature ou type de retour d'une fonction inclut une instance d'un type de référence de chaque valeur, la fonction est marquée dans les métadonnées comme nécessitant une gestion spéciale \(avec modreq\).  Cette gestion spéciale est actuellement disponible qu'à des clients Visual C\+\+; d'autres langues ne prennent pas en charge actuellement des fonctions consommantes ou les données qui utilisent les types référence créés avec la sémantique de pile.  
  
 Une raison d'utiliser `gcnew` \(allocation dynamique\) au lieu de la sémantique de pile est si le type n'a aucun destructeur.  En outre, l'utilisation de types de référence créés avec la sémantique de pile dans les signatures de fonction ne seraient pas possibles si vous souhaitez que vos fonctions soient utilisées dans des langages autres que Visual C\+\+.  
  
 Le compilateur ne génère pas de constructeur de copies pour un type de référence.  Par conséquent, si vous définissez une fonction qui utilise un type de référence pour chaque valeur dans la signature, vous devez définir un constructeur de copie pour le type de référence.  Un constructeur de copie pour un type de référence possède une signature au format suivant : `R(R%){}`.  
  
 Le compilateur ne génère pas un opérateur d'affectation par défaut pour un type de référence.  Un opérateur d'affectation vous permet de créer un objet avec la sémantique de pile et de l'initialiser avec un objet existant créé avec la sémantique de pile.  Un opérateur d'affectation pour un type de référence a une signature au format suivant : `void operator=( R% ){}`.  
  
 Si le destructeur de votre type libère les ressources critiques et vous utilisez la sémantique de pile pour les types de référence, vous n'avez pas besoin d'appeler explicitement le destructeur \(ou appeler `delete`\).  Pour plus d'informations sur les destructeurs dans les types de référence, consultez [Destructeurs et finaliseurs dans Visual C\+\+](../misc/destructors-and-finalizers-in-visual-cpp.md).  
  
 Un opérateur d'assignation généré par le compilateur effectuera les règles habituelles standard C\+\+ avec les ajouts suivants :  
  
-   Toutes données membre non statiques dont les type sont des descripteurs à un type de référence sont copiées superficiellement \(traitées comme des données membre non statiques de type pointeur\).  
  
-   Toutes données membre non statiques dont le type est un type de valeur sont copiées superficiellement.  
  
-   Toutes données membre non statiques dont le type est une instance d'un type de référence font appel au constructeur de copie des types de référence.  
  
 Le compilateur fournit également un opérateur unaire d' `%` pour convertir une instance d'un type référence créé avec la sémantique de pile en son type de données sous\-jacent de descripteur.  
  
 Les types de référence suivants ne sont pas disponibles pour une utilisation avec la sémantique de pile:  
  
-   [délégué](../windows/delegate-cpp-component-extensions.md)  
  
-   [Arrays](../windows/arrays-cpp-component-extensions.md)  
  
-   <xref:System.String>  
  
## Exemple  
  
### Description  
 L'exemple de code suivant indique comment déclarer des instances de types de référence avec la sémantique de pile, comment fonctionne l'opérateur d'affectation et de constructeur de copie, et comment initialiser un suivi des références avec le type de référence créé avec la sémantique de pile.  
  
### Code  
  
```  
// stack_semantics_for_reference_types.cpp  
// compile with: /clr  
ref class R {  
public:  
   int i;  
   R(){}  
  
   // assignment operator  
   void operator=(R% r) {  
      i = r.i;  
   }  
  
   // copy constructor  
   R(R% r) : i(r.i) {}  
};  
  
void Test(R r) {}   // requires copy constructor  
  
int main() {  
   R r1;  
   r1.i = 98;  
  
   R r2(r1);   // requires copy constructor  
   System::Console::WriteLine(r1.i);  
   System::Console::WriteLine(r2.i);  
  
   // use % unary operator to convert instance using stack semantics  
   // to its underlying handle  
   R ^ r3 = %r1;  
   System::Console::WriteLine(r3->i);  
  
   Test(r1);  
  
   R r4;  
   R r5;  
   r5.i = 13;  
   r4 = r5;   // requires a user-defined assignment operator  
   System::Console::WriteLine(r4.i);  
  
   // initialize tracking reference  
   R % r6 = r4;  
   System::Console::WriteLine(r6.i);  
}  
```  
  
### Sortie  
  
```  
98  
98  
98  
13  
13  
```  
  
## Voir aussi  
 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)