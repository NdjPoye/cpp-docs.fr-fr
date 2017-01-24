---
title: "Conteneurs&#160;: fichiers compos&#233;s | Microsoft Docs"
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
  - "modes d'accès pour les fichiers (C++)"
  - "documents composés"
  - "fichiers composés"
  - "conteneurs (C++), fichiers composés"
  - "documents (C++), composée"
  - "documents (C++), OLE"
  - "fichiers (C++), composée"
  - "conteneurs OLE, fichiers composés"
  - "documents OLE, fichiers composés"
  - "performances (C++), fichiers composés"
  - "structure de fichiers standardisée (fichiers composés)"
ms.assetid: 8b83cb3e-76c8-4bbe-ba16-737092b36f49
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Conteneurs&#160;: fichiers compos&#233;s
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique les composants et l'implémentation des fichiers composites et les avantages et les inconvénients liés à l'utilisation de fichiers composites dans vos applications OLE.  
  
 Les fichiers font partie intégrante d'OLE.  Ils permettent de simplifier le transfert de données et le stockage de documents OLE.  Les fichiers composites sont une implémentation de stockage structuré actif.  Des interfaces cohérentes existent qui prennent en charge cette sérialisation vers un stockage, un flux de données, ou un fichier objet.  Les fichiers composites sont pris en charge dans la bibliothèque MFC par les classes `COleStreamFile` et `COleDocument`.  
  
> [!NOTE]
>  L'utilisation d'un fichier composite n'implique pas que les informations proviennent d'un document OLE ou d'un document composite.  Les fichiers composites sont simplement l'une des méthodes pour stocker des documents composés, des documents OLE, et d'autres données.  
  
##  <a name="_core_components_of_a_compound_file"></a> Composants d'un fichier composé  
 L'implémentation OLE des fichiers composites utilise trois types d'objets : objets de flux, objets de stockage, et objets `ILockBytes`.  Ces objets sont semblables aux composants d'un système de fichiers standard selon les manières suivantes :  
  
-   Les objets de flux, telles que les fichiers, les données stockés de tout type.  
  
-   Les objets de stockage, comme les répertoires, peuvent contenir d'autres objets de stockage et de flux.  
  
-   Les objets **LockBytes** représente l'interface entre les objets de stockage et le matériel physique.  Ils déterminent comment les octets réels sont écrits dans n'importe quelle unité de stockage auquel l'objet **LockBytes** accède, tel qu'un disque dur ou une zone de mémoire globale.  Pour plus d'informations sur les objets **LockBytes** et l'interface `ILockBytes`, consultez *le guide de référence du programmeur OLE*.  
  
##  <a name="_core_advantages_and_disadvantages_of_compound_files"></a> Avantages et inconvénients des fichiers composites  
 Les fichiers composites fournissent des avantages non disponibles avec les méthodes précédentes de stockage de fichier.  Ces avantages comprennent :  
  
-   Accès incrémentiel de fichier.  
  
-   Modes d'accès au fichier.  
  
-   Standardisation de la structure d'un fichier.  
  
 Les inconvénients potentiels des fichiers composites — taille importante et problèmes de performances liées au stockage sur les disquettes — doivent être pris en compte lorsque vous décidez si vous allez les utiliser ou non dans votre application.  
  
###  <a name="_core_incremental_access_to_files"></a> Accès aux fichiers incrémentiel  
 L'accès aux fichiers incrémentiel est un avantage automatique de l'utilisation de fichiers composites.  Comme un fichier composé peut être affiché sous la forme d'un « système de fichiers dans un fichier », de différents types d'objets, tels que le flux de données ou le stockage, il est possible d'accéder sans avoir besoin de charger le fichier complet.  Cela peut excessivement réduire le temps où une application doit accéder à des objets pour permettre l'utilisateur de les modifier.  La mise à jour incrémentielle, selon le même concept, présente des avantages similaires.  Au lieu d'enregistrer le fichier entier uniquement pour enregistrer les modifications apportées à un objet OLE, stocke uniquement l'objet de flux de données ou de stockage modifié par l'utilisateur.  
  
###  <a name="_core_file_access_modes"></a> Modes d'accès au fichier.  
 Pouvoir déterminer quand les modifications apportées aux objets d'un fichier composé sont validées sur le disque est un autre avantage des fichiers composites.  Le mode dans lequel les fichiers sont accessibles, soit de manière directe soit après traitement, détermine le moment où les modifications sont validées.  
  
-   Le mode de traitement utilise une opération de validation en deux phases pour modifier les objets dans un fichier composé, en gardant ainsi disponibles les copies anciennes et nouvelles du document jusqu'à ce que l'utilisateur choisisse soit d'enregistrer soit d'annuler les modifications.  
  
-   Le mode direct intègre les modifications apportées au document à mesure qu'elles sont effectuées, sans possibilité de les annuler ultérieurement.  
  
 Pour plus d'informations sur les modes d'accès, consultez *le guide de référence du programmeur OLE*.  
  
###  <a name="_core_standardization"></a> Normalisation  
 La structure standardisée des fichiers composites permet à des applications OLE de parcourir les fichiers composites créés par votre application OLE sans connaissance de l'application qui a réellement créé le fichier.  
  
###  <a name="_core_size_and_performance_considerations"></a> Considérations sur les performances et la taille  
 Du fait de la complexité de la structure de stockage de fichier composé et la possibilité d'enregistrer des données de façon incrémentielle, les fichiers de format sont susceptibles d'être plus grands que d'autres fichiers utilisant du stockage non structuré ou de « fichier plat ».  Si votre application charge et inscrit souvent les fichiers, le recours aux fichiers composites peut entraîner l'augmentation de la taille de fichier beaucoup plus rapidement que les fichiers non composites.  Puisque les fichiers composites peuvent être volumineux, le temps d'accès des fichiers stockés sur et chargé à partir des disquettes peut également être affecté, ce qui donne un accès plus lent aux fichiers.  
  
 L'autre rubrique qui affecte les performances est la fragmentation de fichier composés.  La taille d'un fichier composé est déterminée par la différence entre le premier et le dernier secteur de disque utilisé par le fichier.  Un fichier fragmenté peut contenir plusieurs zones d'espace libre qui ne contiennent pas de données, mais qui sont comptées lors du calcul de la taille.  Pendant la durée de vie d'un fichier composé, ces zones sont créées par l'insertion ou la suppression d'objets de stockage.  
  
##  <a name="_core_using_compound_files_format_for_your_data"></a> Utilisation du format de fichiers composites pour vos données  
 Après avoir créer avec succès une application qui possède une classe de document dérivé de `COleDocument`, assurez\-vous que le constructeur de votre document principal appelle `EnableCompoundFile`.  Lorsque l'Assistant d'application crée des applications de conteneur OLE, cet appel est inséré automatiquement.  
  
 Dans *la référence du programmeur OLE*, consultez [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034), [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015), et l' [ILockBytes](http://msdn.microsoft.com/library/windows/desktop/aa379238).  
  
## Voir aussi  
 [Conteneurs](../mfc/containers.md)   
 [Conteneurs : problèmes d'interface utilisateur](../mfc/containers-user-interface-issues.md)   
 [COleStreamFile Class](../mfc/reference/colestreamfile-class.md)   
 [COleDocument Class](../mfc/reference/coledocument-class.md)