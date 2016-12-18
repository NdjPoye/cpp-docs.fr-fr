---
title: "Sp&#233;cification de niveaux de fonctionnalit&#233; | Microsoft Docs"
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
  - "CObject (classe), ajouter des fonctionnalités aux classes dérivées"
  - "prise en charge de la création dynamique"
  - "niveaux (C++)"
  - "niveaux (C++), fonctionnalités dans CObject"
  - "runtime (C++), informations de classe"
  - "Runtime (classe), prise en charge des informations"
  - "sérialisation (C++), Cobject"
ms.assetid: 562669ba-c858-4f66-b5f1-b3beeea4f486
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Sp&#233;cification de niveaux de fonctionnalit&#233;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment ajouter des niveaux de fonctionnalité à votre [CObject](../mfc/reference/cobject-class.md)\- classe dérivée :  
  
-   [informations de classe d'exécution](#_core_to_add_run.2d.time_class_information)  
  
-   [Prise en charge de la création dynamique](#_core_to_add_dynamic_creation_support)  
  
-   [Prise en charge de sérialisation](#_core_to_add_serialization_support)  
  
 Pour obtenir une description générale de la fonctionnalité de `CObject`, consultez l'article [Dérivation d'une classe de CObject](../mfc/deriving-a-class-from-cobject.md).  
  
#### Pour ajouter des informations sur la classe d'exécution  
  
1.  Dériver la classe à partir de `CObject`, comme décrit dans l'article [Dérivation d'une classe de CObject](../mfc/deriving-a-class-from-cobject.md).  
  
2.  Utilisez la macro `DECLARE_DYNAMIC` dans votre déclaration de classe, comme indiqué ici :  
  
     [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/CPP/specifying-levels-of-functionality_1.h)]  
  
3.  Utilisez la macro `IMPLEMENT_DYNAMIC` dans le fichier d'implémentation \(.CPP\) de la classe.  Cette macro prend comme arguments le nom de la classe et la classe de base, comme suit :  
  
     [!code-cpp[NVC_MFCCObjectSample#3](../mfc/codesnippet/CPP/specifying-levels-of-functionality_2.cpp)]  
  
> [!NOTE]
>  Mettez toujours `IMPLEMENT_DYNAMIC` dans le fichier d'implémentation \(.CPP\) pour la classe.  La macro `IMPLEMENT_DYNAMIC` doit être évaluée une seule fois pendant la compilation et ne doit donc pas être utilisée dans un fichier \(de l'interface. H\) qui pourrait être inclus dans plusieurs fichiers.  
  
#### Pour ajouter la prise en charge de création dynamique  
  
1.  Dérivez vous classe à partir de `CObject`.  
  
2.  Utilisez la macro `DECLARE_DYNCREATE` dans la déclaration de classe.  
  
3.  Définissez un constructeur avec aucun argument \(un constructeur par défaut\).  
  
4.  Utilisez la macro `IMPLEMENT_DYNCREATE` dans le fichier d'implémentation de la classe.  
  
#### Pour ajouter la prise en charge de la sérialisation  
  
1.  Dérivez votre classe à partir de `CObject`.  
  
2.  Ecrasez la fonction membre `Serialize`.  
  
    > [!NOTE]
    >  Si vous appelez `Serialize` directement, c'est\-à\-dire, que vous ne souhaitez pas sérialiser l'objet via un pointeur polymorphe, omettez les étapes 3 à 5.  
  
3.  Utilisez la macro `DECLARE_SERIAL` dans la déclaration de classe.  
  
4.  Définissez un constructeur avec aucun argument \(un constructeur par défaut\).  
  
5.  Utilisez la macro `IMPLEMENT_SERIAL` dans le fichier d'implémentation de la classe.  
  
> [!NOTE]
>  « Points d'un pointeur polymorphe » sur un objet d'une classe \(appel il A\) ou un objet d'une classe dérivée d'Un \(dites, B\).  Pour sérialiser via un pointeur polymorphe, l'infrastructure doit déterminer la classe de l'objet qu'elle sérialise \(b\), ce peut être un objet de n'importe quelle classe dérivée d'une certaine classe de base \(a\).  
  
 Pour plus d'informations sur la manière de vérifier la sérialisation lorsque vous dérivez votre classe `CObject`, consultez les articles [Fichiers de MFC](../mfc/files-in-mfc.md) et [Sérialisation](../mfc/serialization-in-mfc.md).  
  
## Voir aussi  
 [Dérivation d'une classe de CObject](../mfc/deriving-a-class-from-cobject.md)