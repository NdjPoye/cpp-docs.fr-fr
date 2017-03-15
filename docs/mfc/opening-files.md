---
title: "Ouverture de fichiers | Microsoft Docs"
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
  - "CFile (classe), variable"
  - "exemples (MFC), ouvrir des fichiers"
  - "gestion des exceptions (C++), ouvrir des fichiers"
  - "gestion des exceptions (C++), à l'ouverture des fichiers"
  - "objets de fichiers (C++)"
  - "fichiers (C++), ouvrir"
  - "MFC (C++), opérations sur les fichiers"
  - "ouverture (appels)"
  - "ouverture (fonctions membres)"
  - "Open (méthode), CFile (classe)"
  - "ouvrir des fichiers"
  - "ouvrir des fichiers, gérer les exceptions"
  - "ouvrir des fichiers, dans MFC"
ms.assetid: a991b8ec-b04a-4766-b47e-7485b5dd0b01
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Ouverture de fichiers
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans MFC, la façon la plus courante pour ouvrir un fichier est un processus en deux étapes.  
  
#### Pour ouvrir un fichier.  
  
1.  Créez le fichier objet sans spécifier de chemin d'accès ou d'indicateurs d'autorisation.  
  
     Vous créez généralement un objet fichier lorsque vous déclarez une variable [Fichier C](../mfc/reference/cfile-class.md) sur le frame de pile.  
  
2.  Appelez la fonction membre [Ouvrir](../Topic/CFile::Open.md) du fichier objet, en indiquant le chemin d'accès et les indicateurs d'autorisation.  
  
     La valeur de retour pour `Open` est différente de zéro si le fichier a été ouvert correctement ou 0 si le fichier spécifié n'a pas pu être ouvert.  La fonction membre `Open` est prototypée comme suit :  
  
     `virtual BOOL Open( LPCTSTR lpszFileName, UINT nOpenFlags, CFileException* pError = NULL );`  
  
     Les balises ouvertes spécifient quelles autorisations, par exemple en lecture seule, vous souhaitez pour le fichier.  Les valeurs d'indicateur possibles sont définies comme constantes énumérées dans la classe `CFile`, elles sont qualifiées par « `CFile::` » comme dans `CFile::modeRead`.  Utilisez l'indicateur `CFile::modeCreate` si vous souhaitez créer le fichier.  
  
 L'exemple suivant montre comment créer un fichier avec autorisation de lecture\/écriture \(en remplaçant un fichier précédent avec le même chemin d'accès\) :  
  
 [!code-cpp[NVC_MFCFiles#1](../mfc/codesnippet/CPP/opening-files_1.cpp)]  
  
> [!NOTE]
>  Cet exemple crée et ouvre un fichier.  Si il y a des problèmes, l'appel à `Open` peut retourner un objet `CFileException` dans son dernier paramètre, comme illustré ici.  La macro `TRACE` affiche le nom et le code indiquant la raison de l'échec.  Vous pouvez appeler la fonction `AfxThrowFileException` si vous avez besoin d'un rapport d'erreurs plus détaillé.  
  
## Voir aussi  
 [CFile Class](../mfc/reference/cfile-class.md)   
 [CFile::Open](../Topic/CFile::Open.md)   
 [Fichiers](../mfc/files-in-mfc.md)