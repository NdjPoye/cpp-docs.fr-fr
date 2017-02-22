---
title: "&lt;exception&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<exception>"
  - "std::<exception>"
  - "std.<exception>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exception (en-tête)"
ms.assetid: 28900768-5dd7-4834-b907-5e37ab3407db
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# &lt;exception&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit plusieurs types et fonctions relatifs à la gestion des exceptions. La gestion des exceptions est utilisée dans les situations dans lesquelles le système peut récupérer d'une erreur. Elle permet au contrôle d'être retourné au programme depuis une fonction. L'ajout de la gestion des exceptions a pour but d'augmenter la robustesse du programme et de récupérer d'une erreur de façon appropriée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
#include <exception>  
  
```  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[exception_ptr](../Topic/%3Cexception%3E%20typedefs.md#exception_ptr)|Type qui décrit un pointeur vers une exception.|  
|[terminate_handler](../Topic/%3Cexception%3E%20typedefs.md#terminate_handler)|Type qui décrit un pointeur vers une fonction pouvant être utilisée comme un `terminate_handler`.|  
|[unexpected_handler](../Topic/%3Cexception%3E%20typedefs.md#unexpected_handler)|Type qui décrit un pointeur vers une fonction pouvant être utilisée comme un `unexpected_handler`.|  
  
### <a name="functions"></a>Fonctions  
  
|||  
|-|-|  
|[current_exception](../Topic/%3Cexception%3E%20functions.md#current_exception)|Obtient un pointeur vers l'exception actuelle.|  
|[get_terminate](../Topic/%3Cexception%3E%20functions.md#get_terminate)|Obtient la fonction `terminate_handler` actuelle.|  
|[get_unexpected](../Topic/%3Cexception%3E%20functions.md#get_unexpected)|Obtient la fonction `unexpected_handler` actuelle.|  
|[make_exception_ptr](../Topic/%3Cexception%3E%20functions.md#make_exception_ptr)|Crée un objet `exception_ptr` qui contient une copie d'une exception.|  
|[rethrow_exception](../Topic/%3Cexception%3E%20functions.md#rethrow_exception)|Lève une exception passée comme paramètre.|  
|[set_terminate](../Topic/%3Cexception%3E%20functions.md#set_terminate)|Génère un nouvel appel à `terminate_handler` à l'arrêt du programme.|  
|[set_unexpected](../Topic/%3Cexception%3E%20functions.md#set_unexpected)|Génère un nouveau `unexpected_handler` à appeler en cas d'exception inattendue.|  
|[arrêter](../Topic/%3Cexception%3E%20functions.md#terminate)|Appelle un gestionnaire d'arrêt.|  
|[uncaught_exception](../Topic/%3Cexception%3E%20functions.md#uncaught_exception)|Retourne **true** uniquement si une exception levée est actuellement traitée.|  
|[inattendue](../Topic/%3Cexception%3E%20functions.md#unexpected)|Appelle un gestionnaire d'exceptions inattendues.|  
  
### <a name="classes"></a>Classes  
  
|||  
|-|-|  
|[bad_exception, classe](../standard-library/bad-exception-class.md)|La classe décrit une exception pouvant être levée depuis un `unexpected_handler`.|  
|[exception (classe)](Exception%20Class.xml)|La classe sert de classe de base pour toutes les exceptions levées par certaines expressions et par la bibliothèque C++ standard.|  
  
## <a name="see-also"></a>Voir aussi  
 [Référence de fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque Standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

