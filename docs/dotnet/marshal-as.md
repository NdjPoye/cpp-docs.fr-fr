---
title: "marshal_as | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "marshal_as"
  - "msclr.interop.marshal_as"
  - "msclr::interop::marshal_as"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "marshal_as (modèle) (C++)"
ms.assetid: 2ed717da-2b11-41e5-981d-47d251771989
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# marshal_as
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette méthode convertit les données entre le tas natif et les environnements managés.  
  
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
 Cette méthode est un moyen simple de convertir des données entre le tas natif et les types managés.  Pour déterminer quels types de données sont pris en charge, consultez [Vue d'ensemble du marshaling dans C\+\+](../dotnet/overview-of-marshaling-in-cpp.md).  Certaines conversions de données requièrent un contexte.  Convertissez ces types de données en utilisant [marshal\_context, classe](../dotnet/marshal-context-class.md).  
  
 Si vous essayez de surveiller une paire de types de données non pris en charge, `marshal_as` génèrera une erreur [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) au moment de la compilation.  Lisez le message fourni avec cette erreur pour plus d'informations.  L'erreur `C4996` peut être générée pour plus que des fonctions déconseillées.  Un exemple de ceci essaie de surveiller une paire de types de données non pris en charge.  
  
 La bibliothèque de surveillance consiste en plusieurs fichiers d'en\-tête.  Toute conversion requiert un seul fichier, mais vous pouvez inclure des fichiers supplémentaires si vous avez besoin pour d'autres conversions.  Pour connaître les conversions qui sont associées auxquelles les fichiers, regardez dans la table à `Marshaling Overview`.  Indépendamment de la conversion vous souhaitez faire, la spécification de l'espace de noms est toujours appliquée.  
  
## Exemple  
 Cet exemple surveille depuis `const char*` à une variable de type `System::String`.  
  
```  
// marshal_as_test.cpp  
// compile with: /clr  
#include <stdlib.h>  
#include <string.h>  
#include <msclr\marshal.h>  
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {  
   const char* message = "Test String to Marshal";  
   String^ result;  
   result = marshal_as<String^>( message );  
   return 0;  
}  
```  
  
## Configuration requise  
 **Fichier d'en\-tête :** \<msclr\\marshal.h\>, \<msclr\\marshal\_windows.h\>, \<msclr\\marshal\_cppstd.h\> ou \<msclr\\marshal\_atl.h\>  
  
 **Espace de noms :** msclr::interop  
  
## Voir aussi  
 [Vue d'ensemble du marshaling dans C\+\+](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal\_context, classe](../dotnet/marshal-context-class.md)