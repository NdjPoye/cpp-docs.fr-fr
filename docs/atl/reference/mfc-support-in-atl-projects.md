---
title: "Prise en charge MFC dans les projets ATL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.atl.addmfc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "projets ATL, MFC support"
ms.assetid: f90b4276-cb98-4c11-902c-9ebcfe6f954b
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Prise en charge MFC dans les projets ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Si vous sélectionnez l'option **Prendre en charge les MFC** dans l'Assistant Projet ATL, votre projet déclare l'application en tant qu'objet application MFC \(classe\).  Le projet initialise la bibliothèque MFC et instancie une classe \(la classe *ProjName*\) qui est dérivée de [CWinApp](../../mfc/reference/cwinapp-class.md).  
  
 Cette option est disponible uniquement pour les projets DLL ATL sans attributs.  
  
```  
class CProjNameApp : public CWinApp  
{  
public:  
  
// Overrides  
   virtual BOOL InitInstance();  
   virtual int ExitInstance();  
   DECLARE_MESSAGE_MAP()  
};  
  
BEGIN_MESSAGE_MAP(CProjNameApp, CWinApp)  
END_MESSAGE_MAP()  
  
CProjNameApp theApp;  
  
BOOL CProjNameApp::InitInstance()  
{  
   return CWinApp::InitInstance();  
}  
  
int CProjNameApp::ExitInstance()  
{  
   return CWinApp::ExitInstance();  
}  
```  
  
 Vous pouvez afficher la classe de l'objet application ainsi que ses fonctions `InitInstance` et `ExitInstance` dans la fenêtre Affichage de classes.  
  
## Voir aussi  
 [Ajout d'une classe](../../ide/adding-a-class-visual-cpp.md)   
 [Création d'un projet ATL](../../atl/reference/creating-an-atl-project.md)   
 [Configurations des projets ATL par défaut](../../atl/reference/default-atl-project-configurations.md)