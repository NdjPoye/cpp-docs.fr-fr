---
title: "Acc&#232;s aux informations de classe d&#39;ex&#233;cution | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes (C++), informations de classe d'exécution"
  - "CObject (classe), accéder aux informations de classe d'exécution"
  - "CObject (classe), et RTTI"
  - "CObject (classe), utiliser la méthode IsKindOf"
  - "CObject (classe), utiliser la macro RUNTIME_CLASS"
  - "méthode IsKindOf (méthode)"
  - "RTTI (option du compilateur)"
  - "au moment de l'exécution"
  - "au moment de l'exécution, informations de classe"
  - "Runtime (classe)"
  - "Runtime (classe), accéder aux informations"
  - "RUNTIME_CLASS (macro)"
  - "RUNTIME_CLASS (macro), utilisation"
ms.assetid: 3445a9af-0bd6-4496-95c3-aa59b964570b
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Acc&#232;s aux informations de classe d&#39;ex&#233;cution
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment accéder aux informations sur la classe d'un objet au moment de l'exécution.  
  
> [!NOTE]
>  MFC n'utilise pas la prise en charge de [Run\-Time Type Information](../cpp/run-time-type-information.md) \(RTTI\) introduite dans Visual C\+\+ 4.0.  
  
 Si vous avez dérivé votre classe de [CObject](../mfc/reference/cobject-class.md) et avez utilisé **DECLARE**\_**DYNAMIC** et `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE` et `IMPLEMENT_DYNCREATE`, ou les macros `DECLARE_SERIAL` et `IMPLEMENT_SERIAL` expliquées dans l'article [Dérivation d'une classe de CObject](../mfc/deriving-a-class-from-cobject.md), la classe `CObject` est capable de déterminer la classe spécifique d'un objet au moment de l'exécution.  
  
 Cette possibilité est très utile lorsqu'une vérification supplémentaire des types des arguments de la fonction est nécessaire et lorsque vous devez écrire un code spécial en fonction de la classe d'un autre objet.  Toutefois, cette pratique n'est généralement pas recommandée car elle duplique les fonctionnalités des fonctions virtuelles.  
  
 La méthode `IsKindOf` de `CObject` peut être utilisée pour déterminer si un objet particulier appartient à une classe spécifiée ou si elle est dérivée d'une classe spécifique.  L'argument de `IsKindOf` est un objet `CRuntimeClass`, que vous pouvez obtenir à l'aide de la macro `RUNTIME_CLASS` avec le nom de la classe.  
  
### Pour utiliser la macro RUNTIME\_CLASS  
  
1.  Utilisez `RUNTIME_CLASS` avec le nom de la classe, comme indiqué ici pour la classe `CObject`:  
  
     [!code-cpp[NVC_MFCCObjectSample#4](../mfc/codesnippet/CPP/accessing-run-time-class-information_1.cpp)]  
  
 Vous devrez rarement accéder à l'objet de classe d'exécution directement.  Un usage plus courant consiste à passer l'objet de classe d'exécution à la fonction `IsKindOf`, comme le montre la procédure suivante.  La fonction `IsKindOf` teste un objet pour voir s'il appartient à une classe donnée.  
  
#### Pour utiliser la fonction IsKindOf  
  
1.  Vérifiez que la classe possède la prise en charge de la classe d'exécution.  Autrement dit, la classe doit avoir été dérivée directement ou indirectement de `CObject` et utilisé **DECLARE**\_**DYNAMIC** et `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE` et `IMPLEMENT_DYNCREATE`, ou les macros `DECLARE_SERIAL` et `IMPLEMENT_SERIAL` expliquées dans l'article [Dérivation d'une classe de CObject](../mfc/deriving-a-class-from-cobject.md).  
  
2.  Appelez la méthode `IsKindOf` pour les objets de cette classe, à l'aide de la macro `RUNTIME_CLASS` pour générer l'argument `CRuntimeClass`, comme indiqué ici :  
  
     [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/CPP/accessing-run-time-class-information_2.h)]  
  
     [!code-cpp[NVC_MFCCObjectSample#5](../mfc/codesnippet/CPP/accessing-run-time-class-information_3.cpp)]  
  
    > [!NOTE]
    >  IsKindOf retourne **TRUE** si l'objet est un membre de la classe spécifiée ou d'une classe dérivée de la classe spécifiée.  `IsKindOf` ne prend pas en charge l'héritage multiple ou les classes de base virtuelles, bien que vous puissiez utiliser l'héritage multiple pour vos classes dérivées Microsoft Foundation si nécessaire.  
  
 Une utilisation des informations sur la classe d'exécution est en création dynamique des objets.  Ce processus est traité dans l'article [Création d'objet dynamique](../mfc/dynamic-object-creation.md).  
  
 Pour plus d'informations détaillées sur la sérialisation et les informations de classe d'exécution, consultez les articles [Fichiers de MFC](../mfc/files-in-mfc.md) et [Sérialisation](../mfc/serialization-in-mfc.md).  
  
## Voir aussi  
 [Utilisation de CObject](../mfc/using-cobject.md)