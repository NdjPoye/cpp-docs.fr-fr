---
title: "Versions d&#39;AFXDLL | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "afxdll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AFXDLL (bibliothèque)"
  - "Assistants Application (C++), utilisation d'AFXDLL par défaut"
  - "version DLL de MFC (C++)"
  - "MFC (C++), version d'AFXDLL"
  - "DLL MFC (C++), liaison dynamique à la bibliothèque"
  - "bibliothèques MFC (C++), liaison dynamique"
ms.assetid: c078ae8f-85a9-43cb-9ded-c09ca2c45723
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Versions d&#39;AFXDLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Au lieu de générer votre application en liant statiquement des bibliothèques de code objet de MFC, vous pouvez générer votre application en utilisant l'une des bibliothèques de AFXDLL, qui contiennent MFC dans une DLL que plusieurs applications peuvent partager.  Pour une table de noms d'AFXDLL, consultez [DLL : Conventions d'affectation des noms](../build/naming-conventions-for-mfc-dlls.md).  
  
> [!NOTE]
>  Par défaut, le créateur d'Application MFC crée un projet AFXDLL.  Pour utiliser la liaison statique de code de MFC à la place, définissez l'option **Utiliser les MFC dans une bibliothèque statique** dans le créateur d'Application MFC.  La liaison statique n'est pas disponible dans l'Edition Standard de Visual C\+\+.  
  
## Voir aussi  
 [Versions de bibliothèque MFC](../mfc/mfc-library-versions.md)