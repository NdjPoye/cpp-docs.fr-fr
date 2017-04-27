---
title: "Erreur LNK1104 des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1104
dev_langs:
- C++
helpviewer_keywords:
- LNK1104
ms.assetid: 9ca6f929-0efc-4055-8354-3cf5b4e636dc
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 4bac7b2942f9d72674b8092dc7bf64174dd3c349
ms.openlocfilehash: 7fce9c60da4bceafb9ee81231a8630acb4397d83
ms.lasthandoff: 04/24/2017

---
# <a name="linker-tools-error-lnk1104"></a>Erreur des outils Éditeur de liens LNK1104
Impossible d’ouvrir le fichier '*nom de fichier*'  
  
L’éditeur de liens n’a pas pu ouvrir le fichier spécifié.  
  
Pour corriger cette erreur, recherchez les causes possibles suivantes :  
  
-   Le fichier *nom de fichier* n’existe pas. Si votre projet dépend d’un autre projet pour générer ce fichier, assurez-vous que les dépendances de projet sont correctement définies.  
  
-   Lorsque vous spécifiez des bibliothèques dans la boîte de dialogue Pages de propriétés d’un projet, les noms de bibliothèques doivent être séparés par des espaces, et non par des virgules.  
  
-   Le nom de fichier ou le chemin d’accès spécifié sur la ligne de commande est incorrect, ou le chemin d’accès a une spécification de lecteur non valide. Vérifiez l’orthographe et le nom de fichier et l’emplacement. Si vous générez un projet qui a été copié à partir d’un autre ordinateur, vérifiez les chemins d’accès sur le [Page de propriétés répertoires VC ++](../../ide/vcpp-directories-property-page.md) et les mettre à jour si nécessaire.  
  
-   Les bibliothèques pour la configuration de projet ou un ensemble d’outils de plateforme ne sont pas installés. Vérifiez que le système d’exploitation est installé les outils de plateforme et le Kit de développement logiciel Windows spécifié dans les Pages de propriétés pour votre projet et qu’il contient l’ensemble d’outils et des bibliothèques requis par vos paramètres de configuration. Il existe des paramètres distincts pour les configurations Debug et la vente au détail, par conséquent, si une build fonctionne, mais que l’autre provoque une erreur, vérifiez les paramètres sont corrects et les outils requis sont installés pour les deux configurations.  
  
-   Vous n’avez pas suffisamment d’espace disque. Il n’est pas rare pour consommer une grande quantité d’espace disque temporaire au cours d’un lien de l’éditeur de liens.  
  
-   Vous disposez des autorisations de fichier est insuffisante pour accéder à *nom de fichier*.  
  
-   Le chemin d’accès pour *nom de fichier* s’étend sur plus de 260 caractères. Modifier les noms ou réorganiser votre structure de répertoires si nécessaire pour raccourcir les chemins d’accès aux fichiers requis.  
  
-   Si le *nom de fichier* est nommé LNK*n*, qui est un nom de fichier généré par l’éditeur de liens pour un fichier temporaire, le répertoire spécifié dans la variable d’environnement TMP n’existe pas, ou plusieurs répertoires peut être spécifié pour la variable d’environnement TMP. Chemin d’accès d’un seul répertoire doit être spécifié pour la variable d’environnement TMP.  
  
-   Si le message d’erreur s’affiche pour un nom de bibliothèque et que vous avez porté récemment le fichier .mak à partir d’un système de développement Microsoft Visual C++ antérieur, la bibliothèque n’est peut-être plus valide. Vérifiez que le nom de la bibliothèque est correct et qu’il existe toujours dans l’emplacement spécifié, ou mettre à jour le chemin d’accès LIB pour pointer vers le nouvel emplacement.  
  
-   Un autre programme a peut-être ouvert le fichier et l’éditeur de liens ne peut pas y accéder en écriture. Les programmes antivirus souvent bloquent temporairement l’accès aux fichiers qui vient d’être créés. Essayez excluant les répertoires de génération de projet à partir de l’antivirus.  
  
-   Vous disposez d’une variable d’environnement LIB incorrecte. Pour plus d’informations sur la façon de mettre à jour la variable d’environnement LIB, consultez [Page de propriétés répertoires VC ++](../../ide/vcpp-directories-property-page.md). Assurez-vous que tous les répertoires contenant les bibliothèques dont vous avez besoin sont répertoriés ici.  
  
-   L’éditeur de liens utilise des fichiers temporaires dans plusieurs cas. Même si vous disposez de suffisamment d’espace disque, un lien très volumineux peut épuiser ou fragmenter l’espace disque disponible. Envisagez d’utiliser le [/OPT (optimisations)](../../build/reference/opt-optimizations.md) option ; les lectures comdat transitive élimination tous les fichiers objets plusieurs fois.
