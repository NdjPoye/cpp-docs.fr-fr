---
title: "marshal_context::marshal_as | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "marshal_context::marshal_as"
  - "marshal_context.marshal_as"
  - "msclr.interop.marshal_context.marshal_as"
  - "msclr::interop::marshal_context::marshal_as"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "marshal_context (classe) (C++), opérations"
ms.assetid: 24a1afee-51c0-497c-948c-f77fe43635c8
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# marshal_context::marshal_as
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Effectue le marshaling sur un objet de données spécifique pour le convertir entre des types de données managé et natif.  
  
## Syntaxe  
  
```  
To_Type marshal_as<To_Type>(  
   From_Type input   
);  
```  
  
#### Paramètres  
 \[in\] `input`  
 La valeur que vous voulez surveiller à une variable `To_Type`.  
  
## Valeur de retour  
 Une variable de type `To_Type` qui est la valeur convertie de `input`.  
  
## Notes  
 Cette fonction effectue le marshaling sur un objet de données spécifique.  Utilisez cette fonction uniquement avec les conversions répertoriées dans la table dans [Vue d'ensemble du marshaling dans C\+\+](../dotnet/overview-of-marshaling-in-cpp.md).  
  
 Si vous essayez de surveiller une paire de types de données non pris en charge, `marshal_as` génèrera une erreur [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) au moment de la compilation.  Lisez le message fourni avec cette erreur pour plus d'informations.  L'erreur `C4996` peut être générée pour plus que des fonctions déconseillées.  Deux conditions qui génèrent cette erreur essaient de marshaler une paire de types de données qui ne sont pas pris en charge et essaient d'utiliser `marshal_as` pour une conversion qui requiert un contexte.  
  
 La bibliothèque de surveillance consiste en plusieurs fichiers d'en\-tête.  Toute conversion requiert un seul fichier, mais vous pouvez inclure des fichiers supplémentaires si vous avez besoin pour d'autres conversions.  La table dans `Marshaling Overview in C++` indique lequel des fichiers de marshaling doit être inclus pour chaque conversion.  
  
## Exemple  
 Cet exemple crée un contexte pour marshaler d'un `System::String` à un type de variable d' `const char *`.  Les données converties ne sont pas valides après la ligne qui supprime le contexte.  
  
```  
// marshal_context_test.cpp  
// compile with: /clr  
#include <stdlib.h>  
#include <string.h>  
#include <msclr\marshal.h>  
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {  
   marshal_context^ context = gcnew marshal_context();  
   String^ message = gcnew String("Test String to Marshal");  
   const char* result;  
   result = context->marshal_as<const char*>( message );  
   delete context;  
   return 0;  
}  
```  
  
## Configuration requise  
 **Fichier d'en\-tête :** \<msclr\\marshal.h\>, \<msclr\\marshal\_windows.h\>, \<msclr\\marshal\_cppstd.h\> ou \<msclr\\marshal\_atl.h\>  
  
 **Espace de noms :** msclr::interop  
  
## Voir aussi  
 [Vue d'ensemble du marshaling dans C\+\+](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal\_as](../dotnet/marshal-as.md)   
 [marshal\_context, classe](../dotnet/marshal-context-class.md)