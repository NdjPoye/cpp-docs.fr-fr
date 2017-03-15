---
title: "G&#233;n&#233;ration de fichiers d&#39;informations de consultation&#160;: vue d&#39;ensemble | Microsoft Docs"
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
  - "fichiers .bsc, à propos des fichiers .bsc"
  - "fichiers d'informations de consultation (.bsc)"
  - "fichiers d'informations de consultation (.bsc), créer"
  - "fichiers bsc, à propos des fichiers bsc"
ms.assetid: b5c12832-51f6-4953-8044-4264dd0fb242
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# G&#233;n&#233;ration de fichiers d&#39;informations de consultation&#160;: vue d&#39;ensemble
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pour créer des informations de consultation de symboles, le compilateur crée un fichier .sbr associé à chaque fichier source du projet, puis BSCMAKE.EXE concatène tous les fichiers .sbr en un fichier .bsc unique.  
  
 La génération des fichiers .sbr et .bsc prend du temps ; c'est pourquoi Visual C\+\+ désactive ces fonctions par défaut.  Pour consulter les informations en cours, vous devez activer les options de navigation et générer à nouveau le projet.  
  
 Utilisez l'option [\/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) ou [\/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md) pour demander au compilateur de créer des fichiers .sbr.  Pour créer les fichiers .bsc, vous pouvez appeler [BSCMAKE](../../build/reference/bscmake-command-line.md) à partir de la ligne de commande.  En utilisant BSCMAKE depuis la ligne de commande, vous pouvez exercer un contrôle plus précis sur la manipulation des fichiers d'informations de consultation.  Pour plus d'informations, reportez\-vous à [Référence de BSCMAKE](../../build/reference/bscmake-reference.md).  
  
> [!TIP]
>  Vous pouvez activer la génération de fichiers .sbr et laisser désactivée la fonction de génération du fichier .bsc.  Vous bénéficierez d'une bonne vitesse de génération et pourrez créer rapidement un fichier .bsc actualisé en activant la fonction correspondante lors de la génération du projet.  
  
 Il est possible de réduire le temps, la mémoire et l'espace disque nécessaires à la génération du fichier .bsc en diminuant la taille de ce fichier.  
  
 Pour plus d'informations sur la manière de générer un fichier browser dans l'environnement de développement, consultez [Général, page de propriétés \(Projet\)](../../ide/general-property-page-project.md).  
  
### Pour créer un fichier .bsc de plus petite taille  
  
1.  Utilisez les [options de ligne de commande de BSCMAKE](../../build/reference/bscmake-options.md) pour exclure des informations du fichier d'informations de consultation.  
  
2.  Choisissez d'omettre des symboles locaux dans un ou plusieurs fichiers .sbr lors de la compilation ou de l'assemblage.  
  
3.  Si un fichier objet ne contient pas les informations dont vous avez besoin au stade actuel de débogage, omettez son fichier .sbr dans la commande BSCMAKE lorsque vous régénérez le fichier d'informations de consultation.  
  
### Pour combiner les informations de consultation de plusieurs projets en un fichier browser \(.bsc\) unique  
  
1.  Ne générez pas le fichier .bsc au niveau du projet ou utilisez le commutateur \/n pour empêcher la troncation des fichiers .sbr.  
  
2.  Après avoir généré tous les projets, exécutez BSCMAKE avec tous les fichiers .sbr en entrée.  Les caractères génériques sont acceptés.  Par exemple, si vos répertoires de projet C:\\X, C:\\Y et C:\\Z contiennent des fichiers .sbr que vous souhaitez combiner en un fichier .bsc unique, utilisez BSCMAKE C:\\X\\\*.sbr C:\\Y\\\*.sbr C:\\Z\\\*.sbr \/o c:\\répertoire\_quelconque\\fichier\_combiné.bsc pour générer le fichier .bsc combiné.  
  
## Voir aussi  
 [Outils de génération C\/C\+\+](../../build/reference/c-cpp-build-tools.md)   
 [Référence BSCMAKE](../../build/reference/bscmake-reference.md)