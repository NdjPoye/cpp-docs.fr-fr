---
title: "Utilisation d&#39;un contr&#244;le utilisateur Windows Form dans MFC | Microsoft Docs"
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
  - "MFC (C++), prise en charge Windows Forms"
  - "interopérabilité (C++), Windows Forms dans MFC"
  - "interopérabilité (C++), MFC"
  - "Interop (C++), Windows Forms dans MFC"
  - "Interop (C++), MFC"
  - "Windows Forms (C++), MFC prend en charge"
ms.assetid: 63fb099b-1dff-469c-9e34-dab52e122fcd
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Utilisation d&#39;un contr&#244;le utilisateur Windows Form dans MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

À l’aide des classes de prise en charge MFC Windows Forms, vous pouvez héberger des contrôles Windows Forms dans vos applications MFC comme contrôle ActiveX dans des vues ou des boîtes de dialogue MFC. En outre, les formulaires Windows Forms peuvent être hébergés comme boîtes de dialogue MFC.  
  
 Les sections suivantes décrivent comment :  
  
-   Héberger un contrôle Windows Forms dans une boîte de dialogue MFC.  
  
-   Héberger un contrôle utilisateur Windows Forms en tant que vue MFC.  
  
-   Héberger un formulaire Windows Forms sous la forme d’une boîte de dialogue MFC.  
  
> [!NOTE]
>  Intégration de MFC Windows Forms fonctionne uniquement dans les projets qui se lient dynamiquement avec MFC (projets dans lesquels AFXDLL est défini).  
  
> [!NOTE]
>  Lorsque vous générez votre application à l’aide d’une copie privée (modifiée) des interfaces MFC Windows Forms DLL (mfcmifc80.dll), il ne s’installe dans le GAC, sauf si vous remplacez la clé Microsoft par votre propre clé de fournisseur. Pour plus d’informations sur la signature d’assembly, consultez [programmation avec des assemblys](../Topic/Programming%20with%20Assemblies.md) et [les assemblys de nom fort (signature d’Assembly) (C + c++ / CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).  
  
 Pour plus d’exemples d’applications à l’aide de Windows Forms, consultez [BirthdayPicker, exemple : illustre les ressources du .NET Framework avec Windows Forms](http://msdn.microsoft.com/fr-fr/ac932aed-5502-4667-be29-709bca435317), [exemple Calculator : calculatrice de poche Windows Forms](http://msdn.microsoft.com/fr-fr/2283b516-3b7e-45f2-80c4-fdcfb366ce25), et [exemple Scribble : Application de dessin MDI](http://msdn.microsoft.com/fr-fr/f025da3e-659b-4222-b991-554a1b8b2358).  
  
 Pour un exemple d’application illustrant des Windows Forms avec les MFC, consultez [intégration de Windows Forms et MFC](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).  
  
 Si votre application MFC utilise Windows Forms, vous devez redistribuer mfcmifc90.dll avec votre application. Pour plus d’informations, consultez [redistribuer la bibliothèque MFC](../ide/redistributing-the-mfc-library.md).  
  
## <a name="in-this-section"></a>Dans cette section  
 [Hébergement d’un contrôle Windows Form utilisateur dans la boîte de dialogue MFC](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)  
  
 [Hébergement d’un contrôle utilisateur Windows Forms en tant que vue MFC](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)  
  
 [Hébergement d’un contrôle utilisateur Windows Form en tant que boîte de dialogue MFC](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)  
  
## <a name="reference"></a>Référence  
 [CWinFormsControl (classe)](../mfc/reference/cwinformscontrol-class.md)  
  
 [CWinFormsDialog (classe)](../mfc/reference/cwinformsdialog-class.md)  
  
 [Classe CWinFormsView](../mfc/reference/cwinformsview-class.md)  
  
 [Interface de ICommandSource](../mfc/reference/icommandsource-interface.md)  
  
 [Interface de ICommandTarget](../mfc/reference/icommandtarget-interface.md)  
  
 [Interface de ICommandUI](../mfc/reference/icommandui-interface.md)  
  
 [Interface IView](../mfc/reference/iview-interface.md)  
  
 [CommandHandler](../Topic/CommandHandler%20Delegate.md)  
  
 [CommandUIHandler](../Topic/CommandUIHandler%20Delegate.md)  
  
 [DDX_ManagedControl](../Topic/DDX_ManagedControl.md)  
  
 [UICheckState](../Topic/UICheckState%20Enumeration.md)  
  
## <a name="related-sections"></a>Rubriques connexes  
 [Windows Forms](../Topic/Windows%20Forms.md)  
  
 [Contrôles Windows Forms](../Topic/Windows%20Forms%20Controls.md)  
  
 [Contrôles utilisateur ASP.NET](../Topic/ASP.NET%20User%20Controls.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Éléments d’Interface utilisateur](../mfc/user-interface-elements-mfc.md)   
 [Mode formulaire](../mfc/form-views-mfc.md)