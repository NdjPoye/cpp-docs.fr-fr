---
title: "Impossible de copier le composant ’nom_fichier_composant’ de l’assembly multifichier dans le fichier ’nom_fichier_destination’. &lt;reason.&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.cannotcopyscattercomponent"
ms.assetid: 22f851fc-431b-4cdf-9de1-3a29727fa1e6
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Impossible de copier le composant ’nom_fichier_composant’ de l’assembly multifichier dans le fichier ’nom_fichier_destination’. &lt;reason.&gt;
Le composant spécifié n’a pas été copié dans le répertoire bin.  
  
 Certains assemblys sont constitués de plusieurs fichiers. Ce diagnostic est affiché lorsqu’un fichier d’un assembly multifichier ne peut pas être copié dans le répertoire d’exécution.  
  
 Cet échec peut s’expliquer de diverses manières. Par exemple, il peut s’agir d’un manque d’espace disque ou d’un dépassement de la limite MAX\_PATH, associée à la longueur des chemins d’accès. En outre, un processus, éventuellement Visual Studio, peut persister sur le composant ne pouvant pas être copié.  
  
 **Pour corriger cette erreur**  
  
-   Vérifiez que l’espace disque est suffisant.  
  
-   Essayez de déplacer le projet vers un dossier dont le chemin d’accès présente une longueur inférieure à celle du dossier de projet actuel.  
  
-   Remplacez le répertoire de sortie par un dossier dont le chemin d’accès présente une longueur inférieure absolue. Cela s’applique uniquement aux projets clients \(non web\).  
  
-   Redémarrez [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
## Voir aussi  
 [Débogage d'applications Web : erreurs et dépannage](../Topic/Debugging%20Web%20Applications:%20Errors%20and%20Troubleshooting.md)