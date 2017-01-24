---
title: "Membres statiques (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "instances de classe (C++), membres partagés"
  - "instances de classe (C++), membres statiques"
  - "membres de classe (C++), partagés"
  - "membres de classe (C++), static"
  - "données membres (C++), données membres static"
  - "constructeurs d'instance, membres partagés"
  - "constructeurs d'instance, membres statiques"
  - "membres (C++), données membres static"
  - "données membres static (C++)"
  - "membres static (C++), données membres"
ms.assetid: 9cc8cf0f-d74c-46f2-8e83-42d4e42c8370
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Membres statiques (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les classes peuvent contenir des données membres et des fonctions membres statiques.  Quand des données membres sont déclarées comme **statiques**, une seule copie des données est gérée pour tous les objets de la classe.  \(Pour plus d'informations, consultez [Fonctions membres statiques](../misc/static-member-functions.md).\)  
  
 Les données membres statiques ne font pas partie des objets d'un type donné de classe.  Par conséquent, la déclaration de données membres statiques n'est pas considérée comme une définition.  Les données membres sont déclarées dans la portée de classe, mais la définition est exécutée au niveau de la portée de fichier.  Ces membres statiques ont une liaison externe.  L'exemple suivant illustre ce comportement :  
  
```  
// static_data_members.cpp  
class BufferedOutput  
{  
public:  
   // Return number of bytes written by any object of this class.  
   short BytesWritten()  
   {  
      return bytecount;  
   }  
  
   // Reset the counter.  
   static void ResetCount()  
   {  
      bytecount = 0;  
   }  
  
   // Static member declaration.  
   static long bytecount;  
};  
  
// Define bytecount in file scope.  
long BufferedOutput::bytecount;  
  
int main()  
{  
}  
```  
  
 Dans le code précédent, le membre `bytecount` est déclaré dans la classe `BufferedOutput`, mais doit être défini en dehors de la déclaration de classe.  
  
 Les données membres statiques peuvent être mentionnées sans faire référence à un objet de type classe.  Le nombre d'octets écrits avec des objets `BufferedOutput` peut être obtenu comme suit :  
  
```  
long nBytes = BufferedOutput::bytecount;  
```  
  
 Pour que le membre statique existe, il n'est pas nécessaire que des objets du type classe existent.  Les membres statiques sont également accessibles en utilisant les opérateurs de sélection de membre \(**.** et **–\>**\).  Exemple :  
  
```  
BufferedOutput Console;  
  
long nBytes = Console.bytecount;  
```  
  
 Dans le cas précédent, la référence à l'objet \(`Console`\) n'est pas évaluée ; la valeur retournée est celle de l'objet statique `bytecount`.  
  
 Les données membres statiques étant soumises à des règles d'accès de membre de classe, l'accès privé à ces données est autorisé uniquement pour les fonctions membres de classe et friend.  Ces règles sont décrites dans [Contrôle d'accès aux membres](../cpp/member-access-control-cpp.md).  L'exception est que les données membres statiques doivent être définies dans la portée de fichier quelles que soient les restrictions d'accès.  Si les données membres doivent être explicitement initialisées, un initialiseur doit être fourni avec la définition.  
  
 Le type d'un membre statique n'est pas qualifié par son nom de classe.  Par conséquent, le type de `BufferedOutput::bytecount` est `long`.  
  
## Voir aussi  
 [Classes et structs](../cpp/classes-and-structs-cpp.md)