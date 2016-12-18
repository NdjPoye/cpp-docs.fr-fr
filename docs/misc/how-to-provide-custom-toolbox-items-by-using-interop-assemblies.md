---
title: "Comment&#160;: fournir des &#233;l&#233;ments de bo&#238;te &#224; outils personnalis&#233;s &#224; l’aide d’assemblys d’interop&#233;rabilit&#233; | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Boîte à outils (SDK Visual Studio), ajout d’éléments à l’aide d’assemblys d’interopérabilité"
ms.assetid: c3e8b404-7086-4e08-9d07-ab9c509963ca
caps.latest.revision: 33
caps.handback.revision: 33
manager: "douge"
---
# Comment&#160;: fournir des &#233;l&#233;ments de bo&#238;te &#224; outils personnalis&#233;s &#224; l’aide d’assemblys d’interop&#233;rabilit&#233;
> [!NOTE]
>  Pour ajouter des contrôles personnalisés à la boîte à outils, il est recommandé d’utiliser les modèles de contrôles de boîte à outils fournis avec le Kit de développement logiciel \(SDK\) Visual Studio 10. Cette rubrique est conservée uniquement pour la compatibilité descendante et l’ajout de contrôles existants à la boîte à outils.  
>   
>  Pour plus d’informations sur la création de contrôles de boîte à outils à l’aide de modèles, consultez [Comment : créer un contrôle de boîte à outils qui utilise Windows Forms](../misc/how-to-create-a-toolbox-control-that-uses-windows-forms.md) et [Création d’un contrôle de boîte à outils WPF](../Topic/Creating%20a%20WPF%20Toolbox%20Control.md).  
  
 Un VSPackage basé sur un assembly d’interopérabilité peut étendre la fonctionnalité de la **boîte à outils** [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] par le biais de l’ajout de contrôles ActiveX.  
  
 Pour obtenir la liste des formats de Presse\-papiers standard de la boîte à outils [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], consultez [Extension de la boîte à outils](../misc/extending-the-toolbox.md).  
  
 Pour plus d’informations sur la façon dont un VSPackage gère la **boîte à outils** à l’aide du [!INCLUDE[vsipsdk](../mfc/includes/vsipsdk_md.md)], consultez [Gestion de la boîte à outils](../misc/managing-the-toolbox.md).  
  
 Pour plus d’informations sur la gestion de la **boîte à outils** via Automation, consultez [Comment : contrôler la boîte à outils](../Topic/How%20to:%20Control%20the%20Toolbox.md).  
  
## Procédures  
 Les éléments ajoutés à la **boîte à outils** doivent implémenter les formats de Presse\-papiers standard de la **boîte à outils**, sauf si le VSPackage qui ajoute les éléments joue le rôle de fournisseur d’éléments de **boîte à outils** \(offrant ainsi une prise en charge de l’implémentation du nouveau format\).  
  
#### Pour implémenter un contrôle de boîte à outils  
  
-   Quand un élément de **boîte à outils** est fourni par un VSPackage implémenté dans du code non managé, il doit implémenter un objet `IDataObject` ou être un contrôle ActiveX, à partir duquel l’environnement peut obtenir un objet `IDataObject`.  
  
     Pour plus d’informations sur l’implémentation de l’objet `IDataObject` pour prendre en charge la **boîte à outils**, consultez <xref:System.Runtime.InteropServices.ComTypes.IDataObject>, <xref:Microsoft.VisualStudio.Shell.Interop.TBXITEMINFO> et <xref:System.Runtime.InteropServices.ComTypes.FORMATETC>.  
  
#### Pour ajouter des contrôles basés sur des assemblys d’interopérabilité à la boîte à outils  
  
1.  Obtenez des instances des interfaces suivantes :  
  
    1.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2>, qui prend en charge l’ajout de contrôles et de sections \(onglets\) à la **boîte à outils**, ainsi que la configuration d’autres aspects de la **boîte à outils**.  
  
    2.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox3>, qui prend en charge la localisation et la persistance des paramètres [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
    > [!NOTE]
    >  L'interface <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2> hérite de l'interface <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox>.<xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox3> ne dérive pas de <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2> et n’implémente pas ses méthodes.  
  
     Les interfaces <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox3> et <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2> sont obtenues en appelant la méthode <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider.QueryService%2A> sur le service <xref:Microsoft.VisualStudio.Shell.Interop.SVsToolbox> à l’aide de l’ID de service `SID_SVsToolbox`.  
  
     L’ID d’interface `IID_IVSToolbox2` permet d’obtenir l’interface <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2>, et l’ID d’interface `IID_IVSToolbox3` retourne <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox3>.  
  
     Dans l’exemple ci\-dessous, l’interface <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2> est obtenue via un appel à `QueryService` et l’interface <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox3> est obtenue en appelant `QueryInterface` sur l’interface <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2>.  
  
    ```cpp  
    extern CComModule _Module;  
    CComPtr<IVsToolbox2> srpTbx2;  
    CComPtr<IVsToolbox3> srpTbx3;  
    hr = _Module.QueryService(SID_SVsToolbox, IID_IVsToolbox2, (void**) &srpTbx2));  
    hr = srpTbx2->QueryInterface( IID_IVsToolbox3, (void **)&srpTbx3)  
    ```  
  
2.  Utilisez les instances des interfaces <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2> et <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox3> pour ajouter des onglets \(sections\) et des contrôles à la **boîte à outils**.  
  
     Dans l’exemple ci\-dessous, la méthode <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2.AddTab%2A> est utilisée pour ajouter un nouvel onglet avec un nom localisé.  
  
     Comme ce nom localisé n’est pas un nom invariant, un nom invariant non localisé \(dans ce cas, `L"HTML"`\) est défini via un appel à la méthode <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox3.SetIDOfTab%2A>.  
  
     Si l’onglet de boîte à outils existe déjà, `AddTab2` retourne l’erreur E\_FAIL. Dans ce cas, l’onglet est supposé avoir été correctement ajouté avant d’effectuer une tentative d’obtention du nom invariant.  
  
     Si l’onglet a bien été ajouté, un contrôle basé sur <xref:System.Runtime.InteropServices.ComTypes.IDataObject> est ajouté à la **boîte à outils**. Sinon, une erreur est renvoyée.  
  
    ```cpp  
    CComBSTR sbstrID;  
    hr = srpTbx2->AddTab2((WCHAR*)szwDisplayTabName, *pclsidPackage);  
    if ( hr == S_OK) {  
        sbstrID =L"HTML";  
        hr = srpTbx3->SetIDOfTab( (WCHAR*)szwDisplayTabName, sbstrID);  
    }else{  
        hr = S_OK;  
        hr = srpTbx3->GetIDOfTab( (WCHAR*)szwDisplayTabName, &sbstrID );  
  
    }  
    if ( hr = S_OK){  
        hr=srpTbx2->AddItem(tbxItem, &tinfo, bstrLabel);  
    }  
    return hr;  
    ```  
  
 Outre l’ajout à la **boîte à outils**, un VSPackage peut être configuré comme fournisseur de données de **boîte à outils** et peut être utilisé pour étendre la prise en charge du glisser\-déplacer à l’IDE [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]. Cela permet d’exposer des formats de Presse\-papiers arbitraires à la **boîte à outils** et aux éditeurs.  
  
#### Pour configurer un VSPackage comme fournisseur d’éléments de boîte à outils  
  
1.  Inscrivez le VSPackage basé sur l’interopérabilité comme fournisseur d’éléments de **boîte à outils**.  
  
     Pour plus d’informations sur l’inscription comme fournisseur d’éléments de **boîte à outils**, consultez [Inscription des fonctionnalités de prise en charge de boîte à outils](../misc/registering-toolbox-support-features.md).  
  
2.  Inscrivez la prise en charge des formats de Presse\-papiers de **boîte à outils** personnalisés.  
  
     Pour les contrôles de prise en charge d’un VSPackage basé sur l’interopérabilité qui n’implémentent pas tous les formats de Presse\-papiers de **boîte à outils** standard ou qui implémentent un format de Presse\-papiers de **boîte à outils** personnalisé, procédez comme suit :  
  
    1.  Inscrivez les formats de Presse\-papiers de boîte à outils qui sont pris en charge. Pour plus d'informations, consultez [Inscription des fonctionnalités de prise en charge de boîte à outils](../misc/registering-toolbox-support-features.md).  
  
    2.  Créez une classe qui implémente les interfaces <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxDataProvider> et <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxDataProvider2>.  
  
        > [!NOTE]
        >  Les interfaces <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxDataProvider> et <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxDataProvider2> ne doivent pas être implémentées dans la classe qui implémente l’interface <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>.  
  
    3.  Ajoutez du code pour informer la boîte à outils qu’une implémentation spécifique des interfaces <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxDataProvider> et <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxDataProvider2> prend en charge les formats de données personnalisés avec <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxDataProviderRegistry.RegisterDataProvider%2A> ou <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox.RegisterDataProvider%2A>, deux méthodes équivalentes.  
  
         La méthode <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox.RegisterDataProvider%2A> est généralement appelée dans l’implémentation de la méthode <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> ou dans la méthode de gestionnaire <xref:Microsoft.VisualStudio.Shell.WindowPane.OnCreate%2A> utilisée lors de l’activation du VSPackage.  
  
        ```cpp  
        CComPtr<IVsToolboxDataProviderRegistry> pTB;  
        if (SUCCEEDED (hr = pServiceProvider->QueryService(SID_SVsToolboxDataProviderRegistry, IID_IVsToolboxDataProviderRegistry, (PVOID*)&pTB)) && pTB != NULL)  
        {  
            CustToolboxDataProvider* pDP = new CustToolboxDataProvider;  
            if (pDP)  
            {  
                pDP->AddRef();  
                VSCOOKIE dwDPCookie; //UNDONE: pass NULL instead of ptr to the cookie when RegisterDataProvider allows it.  
                pTB->RegisterDataProvider((IVsToolboxDataProvider*)pDP, &dwDPCookie);  
                pDP->Release();  
            }  
            else  
            {  
                hr = E_OUTOFMEMORY;  
            }  
        }  
        ```  
  
 Pour obtenir la liste des formats de Presse\-papiers standard de la **boîte à outils** [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], consultez [Extension de la boîte à outils](../misc/extending-the-toolbox.md).  
  
## Voir aussi  
 [Extension de la boîte à outils](../misc/extending-the-toolbox.md)   
 [Procédures pas à pas de la Boîte à outils](../misc/toolbox-walkthroughs.md)   
 [Inscription des fonctionnalités de prise en charge de boîte à outils](../misc/registering-toolbox-support-features.md)   
 [Développement avancé de contrôles de boîte à outils](../misc/advanced-toolbox-control-development.md)   
 [Gestion de la boîte à outils](../misc/managing-the-toolbox.md)   
 [Comment : contrôler la boîte à outils](../Topic/How%20to:%20Control%20the%20Toolbox.md)