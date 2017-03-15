---
title: "Mode d&#39;&#233;valuation des blocs Catch (C++) | Microsoft Docs"
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
  - "gestion d'exceptions C++, catch (gestionnaires)"
  - "catch (mot clé) (C++), types de gestionnaires catch"
  - "gestion des exceptions, intercepter et supprimer des exceptions"
  - "try-catch (mot clé) (C++), types saisissable"
  - "types (C++), gestion des exceptions"
ms.assetid: 202dbf07-8ace-4b3b-b3ae-4b45c275e0b4
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Mode d&#39;&#233;valuation des blocs Catch (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ vous permet de lever des exceptions de tout type, bien qu'en général il soit recommandé de lever des types dérivés de std::exception.  Une exception C\+\+ peut être interceptée par un gestionnaire **catch** qui spécifie le même type que l'exception levée, ou par un gestionnaire qui peut intercepter tout type d'exception.  
  
 Si le type de l'exception levée est une classe, qui possède également une classe \(ou des classes\) de base, elle peut être interceptée par des gestionnaires qui acceptent les classes de base du type de l'exception, ainsi que des références aux bases du type de l'exception.  Notez que lorsqu'une exception est interceptée par une référence, elle est associée à l'objet exception levée réel. Dans le cas contraire, il s'agit d'une copie \(similaire à un argument pour une fonction\).  
  
 Lorsqu'une exception est levée, elle peut être interceptée par les types suivants de gestionnaires **catch** :  
  
-   Gestionnaire capable d'accepter tout type \(à l'aide de la syntaxe avec points de suspension\).  
  
-   Gestionnaire qui accepte le même type que l'objet exception. Comme il s'agit d'une copie, les modificateurs **const** et `volatile` sont ignorés.  
  
-   Gestionnaire qui accepte une référence au même type que l'objet exception.  
  
-   Gestionnaire qui accepte une référence à une forme **const** ou `volatile` du même type que l'objet exception.  
  
-   Gestionnaire qui accepte une classe de base du même type que l'objet exception. Comme il s'agit d'une copie, les modificateurs **const** et `volatile` sont ignorés.  Le gestionnaire **catch** pour une classe de base ne doit pas précéder le gestionnaire **catch** de la classe dérivée.  
  
-   Gestionnaire qui accepte une référence à une classe de base du même type que l'objet exception.  
  
-   Gestionnaire qui accepte une référence à une forme **const** ou `volatile` d'une classe de base du même type que l'objet exception.  
  
-   Gestionnaire qui accepte un pointeur vers lequel un objet pointeur levé peut être converti via des règles de conversion de pointeur standard.  
  
 L'ordre dans lequel les gestionnaires **catch** sont placés est important, car les gestionnaires d'un bloc **try** donné sont examinés dans leur ordre d'apparition.  Par exemple, il est incorrect de placer le gestionnaire d'une classe de base avant le gestionnaire d'une classe dérivée.  Une fois qu'un gestionnaire **catch** correspondant a été trouvé, les gestionnaires suivants ne sont pas examinés.  Par conséquent, un gestionnaire **catch** avec points de suspension doit être le dernier gestionnaire du bloc **try**.  Par exemple :  
  
```  
// ...  
try  
{  
    // ...  
}  
catch( ... )  
{  
    // Handle exception here.  
}  
// Error: the next two handlers are never examined.  
catch( const char * str )  
{  
    cout << "Caught exception: " << str << endl;  
}  
catch( CExcptClass E )  
{  
    // Handle CExcptClass exception here.  
}  
```  
  
 Dans cet exemple, le gestionnaire **catch** avec points de suspension est le seul gestionnaire qui est examiné.  
  
## Voir aussi  
 [Gestion d'exceptions C\+\+](../cpp/cpp-exception-handling.md)