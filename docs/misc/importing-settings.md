---
title: "Importation des param&#232;tres | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "paramètres utilisateur (SDK Visual Studio), importation à l’aide d’une infrastructure de package gérée"
  - "IDE (paramètres), importation à l’aide d’une infrastructure de package gérée"
  - "IDE, importation des paramètres à l’aide d’une infrastructure de package gérée"
  - "infrastructure de package gérée, importation des paramètres d’environnement"
ms.assetid: 943f9a5b-c5a5-45ce-a5a9-8d4c02f15577
caps.latest.revision: 23
caps.handback.revision: 23
manager: "douge"
---
# Importation des param&#232;tres
L’environnement de développement intégré \(IDE\) de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] utilise les classes qui implémentent l’interface <xref:Microsoft.VisualStudio.Shell.IProfileManager> et qui sont inscrites pour prendre en charge l’implémentation d’un VSPackage. Cette implémentation permet d’obtenir l’état d’un VSPackage.  
  
 Étant donné que l’IDE instancie la classe qui implémente l’interface <xref:Microsoft.VisualStudio.Shell.IProfileManager> pour prendre en charge les paramètres [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], l’interface <xref:Microsoft.VisualStudio.Shell.IProfileManager> doit être implémentée dans une classe indépendante.  
  
> [!NOTE]
>  N’implémentez pas <xref:Microsoft.VisualStudio.Shell.IProfileManager> dans la classe qui implémente <xref:Microsoft.VisualStudio.Shell.Package>.  
  
### Pour implémenter l’exportation des paramètres  
  
1.  Déclarez la classe qui implémente les paramètres [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
     Déclarez une classe implémentant <xref:Microsoft.VisualStudio.Shell.IProfileManager> et assignez\-lui un `GUID`.  
  
    > [!NOTE]
    >  Les classes qui implémentent l’interface <xref:Microsoft.VisualStudio.Shell.IProfileManager> doivent également implémenter l’interface <xref:System.ComponentModel.IComponent>, ce qui peut être effectué en dérivant la classe de la classe <xref:System.ComponentModel.Component>.  
  
     Exemple :  
  
    ```  
    [Guid("XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX")]  
    internal class MyPackageProfileManager : Component, IProfileManager   
    ```  
  
2.  Assurez\-vous que la classe qui implémente les paramètres obtient l’état à partir du disque.  
  
     Cette étape s’effectue en implémentant la méthode <xref:Microsoft.VisualStudio.Shell.IProfileManager.LoadSettingsFromXml%2A>.  
  
     Les informations devant être persistantes et la façon dont ces informations sont obtenues et marshalées du VSPackage diffèrent d’un VSPackage à un autre.  
  
     Indépendamment des informations rendues persistantes par le VSPackage, la classe implémentant <xref:Microsoft.VisualStudio.Shell.IProfileManager> doit utiliser l’interface <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsReader> fournie pour obtenir les données du fichier de paramètres.  
  
     En règle générale, comme dans l’exemple ci\-dessous, <xref:Microsoft.VisualStudio.Shell.IProfileManager.LoadSettingsFromXml%2A> se charge également de la validation des données obtenues et de la mise à jour de l’état du VSPackage.  
  
    ```vb#  
    Dim mySvc As MyPackageService = TryCast(GetService(GetType(IVSMDMyPackage)), MyPackageService)   
    If mySvc IsNot Nothing Then   
        Dim value As String   
        Dim myState As StateObject = mySvc.MyPackage.packageState   
        reader.ReadSettingString("PbrsShowDesc", value)   
        If value Is Nothing OrElse value = "" Then   
            reader.ReportError("Unable to Help Visibility Setting")   
        Else   
            myState.HelpVisible = Not value.Equals("0")   
        End If   
        reader.ReadSettingString("PbrsAlpha", value)   
        If value Is Nothing OrElse value = "" Then   
            reader.ReportError("Unable to Retrieve Sort Value")   
        Else   
            If Not value.Equals("0") Then   
                myState.SortState = SortState.Alphabetical   
            Else   
                myState.SortState = SortState.Categorized   
            End If   
        End If   
    End If  
    ```  
  
    ```c#  
    MyPackageService mySvc = GetService(typeof(IVSMDMyPackage)) as MyPackageService;  
    if (mySvc != null){  
      string value;  
      StateObject myState = mySvc.MyPackage.packageState;  
      reader.ReadSettingString("PbrsShowDesc", out value);  
      if (value == null || value == ""){  
          reader.ReportError("Unable to Help Visibility Setting");  
      }else{  
          myState.HelpVisible = !value.Equals("0");  
      }  
      reader.ReadSettingString("PbrsAlpha", out value);  
      if (value == null || value == ""){  
          reader.ReportError("Unable to Retrieve Sort Value");  
      }else{  
        if (!value.Equals("0")){  
          myState.SortState = SortState.Alphabetical;  
        }else{  
          myState.SortState = SortState.Categorized;  
        }  
      }  
    }  
    ```  
  
     Détails de l’implémentation :  
  
    -   Signalez les erreurs à l’utilisateur de manière interactive par le biais de l’IDE en utilisant la méthode <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsReader.ReportError%2A> de l’interface <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsReader> :  
  
        ```vb#  
        reader.ReadSettingString("PbrsAlpha", value)   
        If value Is Nothing OrElse value = "" Then   
            reader.ReportError("Unable to Retrieve Sort Value")   
        End If  
        ```  
  
        ```c#  
          reader.ReadSettingString("PbrsAlpha", out value);  
          if (value == null || value == ""){  
              reader.ReportError("Unable to Retrieve Sort Value");  
          }  
        ```  
  
    -   Préalablement à l’obtention des paramètres stockés, une implémentation de la méthode <xref:Microsoft.VisualStudio.Shell.IProfileManager.LoadSettingsFromXml%2A> doit utiliser la méthode <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsReader.ReadFileVersion%2A> pour vérifier que la version de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] qui exporte les paramètres stockés est prise en charge.  
  
         Dans l’exemple ci\-dessous, l’implémentation vérifie si les paramètres ont été générés par une version de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] avec un numéro de version principale de `m_supportVer`. Si ce n’est pas le cas, elle signale une erreur.  
  
        ```vb#  
        If pnMajor <> m_supportVer Then   
            reader.ReportError("Unsupported Version")   
        End If  
        ```  
  
        ```c#  
        if (pnMajor != m_supportVer){  
          reader.ReportError("Unsupported Version");  
        }  
        ```  
  
    -   Le fichier de paramètres [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] prend en charge l’accès aléatoire aux données. Ainsi, l’ordre des opérations de lecture et d’écriture n’est pas important. Dans l’exemple ci\-dessous, les opérations d’écriture dans l’implémentation de la méthode <xref:Microsoft.VisualStudio.Shell.IProfileManager.SaveSettingsToXml%2A> sont dans l’ordre inverse des opérations de lecture dans la méthode <xref:Microsoft.VisualStudio.Shell.IProfileManager.LoadSettingsFromXml%2A>.  
  
    -   La valeur de l’argument `pszSettingName` fourni à une méthode de l’interface <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsWriter> doit identifier de façon unique chaque élément de données enregistré dans une catégorie de paramètres.  
  
        > [!NOTE]
        >  Les noms doivent être uniques seulement dans la portée de la classe d’implémentation, car l’IDE utilise le GUID de la classe qui implémente les paramètres et la valeur de `pszSettingName` pour identifier chaque paramètre enregistré. Si plusieurs méthodes <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsWriter> sont appelées avec la même valeur de `pszSettingName`, la valeur d’origine est remplacée dans le fichier de paramètres.  
  
3.  Assurez la cohérence entre l’état du VSPackage et les paramètres stockés ou mis en cache localement.  
  
     Cette étape s’effectue généralement pendant l’implémentation de la méthode <xref:Microsoft.VisualStudio.Shell.IProfileManager.SaveSettingsToStorage%2A> \(comme illustré dans l’exemple ci\-dessous\). Les détails de cette étape sont spécifiques à un VSPackage. Vous devrez peut\-être obtenir l’état du VSPackage via Automation, interroger le VSPackage et définir des clés de Registre.  
  
    > [!NOTE]
    >  La méthode <xref:Microsoft.VisualStudio.Shell.IProfileManager.LoadSettingsFromStorage%2A> doit obtenir les informations enregistrées par la méthode <xref:Microsoft.VisualStudio.Shell.IProfileManager.SaveSettingsToStorage%2A> quand la méthode <xref:Microsoft.VisualStudio.Shell.IProfileManager.LoadSettingsFromStorage%2A> est appelée par l’IDE pendant l’initialisation du VSPackage pris en charge.  
  
     Dans l’exemple ci\-dessous, la classe fournissant la prise en charge des paramètres implémente la méthode <xref:Microsoft.VisualStudio.Shell.IProfileManager.SaveSettingsToStorage%2A> pour :  
  
    -   Accéder aux informations mises à jour sur l’état du VSPackage.  
  
        ```vb#  
        Dim mySvc As MyPackageService = TryCast(GetService(GetType(IVSMDMyPackage)), MyPackageService)   
        Dim package As Package = TryCast(GetService(GetType(Package)), Package)   
        Dim rootKey As RegistryKey = package.UserRegistryRoot  
        ```  
  
        ```c#  
        MyPackageService mySvc = GetService(typeof(IVSMDMyPackage)) as MyPackageService;  
        Package package = GetService(typeof(Package)) as Package;  
        RegistryKey rootKey = package.UserRegistryRoot;  
        ```  
  
    -   Utiliser ces informations pour mettre à jour les paramètres de Registre du VSPackage.  
  
        ```vb#  
        If mySvc.MyPackage.packageState IsNot Nothing Then   
            Using rootKey   
                Using pbrsKey As RegistryKey = rootKey.CreateSubKey(Me.[GetType]().Name)   
                    Using pbrsKey   
                        DirectCast(mySvc.MyPackage.packageState, IComPropertyBrowser).SaveState(pbrsKey)   
                    End Using   
                End Using   
            End Using   
        End If  
        ```  
  
        ```c#  
        if (mySvc.MyPackage.packageState != null) {  
          using (rootKey) {  
            using(RegistryKey pbrsKey = rootKey.CreateSubKey(this.GetType().Name)) {  
              using (pbrsKey) {  
                ((IComPropertyBrowser)mySvc.MyPackage.packageState).SaveState(pbrsKey);  
              }  
            }  
          }  
        }  
        ```  
  
    -   > [!NOTE]
        >  La répartition des tâches entre les méthodes <xref:Microsoft.VisualStudio.Shell.IProfileManager.LoadSettingsFromXml%2A> et <xref:Microsoft.VisualStudio.Shell.IProfileManager.SaveSettingsToStorage%2A> varie en fonction de l’implémentation et peut être arbitraire. Par exemple, l’implémentation peut être réécrite avec une implémentation vide de la méthode <xref:Microsoft.VisualStudio.Shell.IProfileManager.LoadSettingsFromStorage%2A>, et toutes les requêtes liées au Registre et à l’état peuvent être effectuées dans la méthode <xref:Microsoft.VisualStudio.Shell.IProfileManager.SaveSettingsToXml%2A>.  
  
4.  Inscrivez la classe qui implémente les paramètres pour prendre en charge un VSPackage.  
  
     Exécutez une instance de <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> construite avec le <xref:System.Type> de la classe qui implémente <xref:Microsoft.VisualStudio.Shell.IProfileManager> dans l’implémentation <xref:Microsoft.VisualStudio.Shell.Package> du VSPackage.  
  
    ```vb#  
    <ProvideProfile(GetType(MyPackageProfileManager), "CoreUI", "MyPackage", 1004, 1004, False)> _   
    <Guid("YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY")> _   
    Class MyPackage   
        Inherits Package   
    End Class  
    ```  
  
    ```c#  
     [ProvideProfile(typeof(MyPackageProfileManager), "CoreUI", "MyPackage", 1004, 1004, false)]  
    [Guid("YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY")]  
    class MyPackage: Package   
    ```  
  
     Dans ce cas, l’attribut informe l’IDE que la classe `MyPackageProfileManager` fournit une implémentation des paramètres à la classe `MyPackage`. Le Point de paramètres personnalisés dans le Registre est créé sous HKLM\\Software\\Microsoft\\VisualStudio\\*\<Version\>*\\UserSettings\\ CoreUI\_MyPackage, où *\<Version\>* correspond à la version de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] \(8.0, par exemple\).  
  
     Pour plus d'informations, voir [Prise en charge pour les paramètres utilisateur](../Topic/Support%20for%20User%20Settings.md) et <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute>.  
  
## Exemple  
 L’exemple suivant implémente <xref:Microsoft.VisualStudio.Shell.IProfileManager> dans une classe :  
  
```vb#  
Imports System   
Imports System.Runtime.InteropServices   
Imports Microsoft.VisualStudio.Shell   
Imports Microsoft.VisualStudio.Shell.Interop   
Imports Microsoft.Win32   
Imports myPackageNameSpace   
Namespace myProfileManagerNameSpace  
  
    <Guid("XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX")> _   
    Friend Class MyPackageProfileManager   
        Inherits System.ComponentModel.Component   
        Implements IProfileManager   
        Friend Const m_supportVer As Integer = 8   
        Public Sub SaveSettingsToXml(ByVal writer As IVsSettingsWriter)   
            Dim mySvc As MyPackageService = TryCast(GetService(GetType(MyPackage)), MyPackageService)   
            If mySvc IsNot Nothing Then   
                ' Information is stored in a StateObject.   
                Dim myState As StateObject = mySvc.MyPackage.packageState   
                writer.WriteSettingString("PbrsAlpha", (If(myState.SortState = SortState.Alphabetical, "1", "0")))   
                writer.WriteSettingString("PbrsShowDesc", (If(myState.HelpVisible, "1", "0")))   
            End If   
        End Sub   
  
        Public Sub LoadSettingsFromXml(ByVal reader As IVsSettingsReader)   
  
            Dim pnMajor As Integer, pnMinor As Integer, pnBuild As Integer   
            ' First check if we are getting data from the correct major version.   
            reader.ReadVersion(pnMajor, pnMinor, pnBuild)   
            If pnMajor <> m_supportVer Then   
                reader.ReportError("Unsupported Version")   
            Else   
                Dim mySvc As MyPackageService = TryCast(GetService(GetType(IVSMDMyPackage)), MyPackageService)   
                If mySvc IsNot Nothing Then   
                    Dim value As String   
                    Dim myState As StateObject = mySvc.MyPackage.packageState   
                    reader.ReadSettingString("PbrsShowDesc", value)   
                    ' Not all values must be present.   
                    If value Is Nothing OrElse value = "" Then   
                        reader.ReportError("Unable to Help Visibility Setting")   
                    Else   
                        myState.HelpVisible = Not value.Equals("0")   
                    End If   
                    reader.ReadSettingString("PbrsAlpha", value)   
                    ' Not all values must be present.   
                    If value Is Nothing OrElse value = "" Then   
                        reader.ReportError("Unable to Retrieve Sort Value")   
                    Else   
                        If Not value.Equals("0") Then   
                            myState.SortState = SortState.Alphabetical   
                        Else   
                            myState.SortState = SortState.Categorized   
                        End If   
                    End If   
                End If   
            End If   
        End Sub   
  
        Public Sub SaveSettingsToStorage()   
            Dim mySvc As MyPackageService = TryCast(GetService(GetType(IVSMDMyPackage)), MyPackageService)   
            Dim package As Package = TryCast(GetService(GetType(Package)), Package)   
            Dim rootKey As RegistryKey = package.UserRegistryRoot   
  
            If mySvc.MyPackage.packageState IsNot Nothing Then   
                Using rootKey   
                    Using pbrsKey As RegistryKey = rootKey.CreateSubKey(Me.[GetType]().Name)   
                        Using pbrsKey   
                            DirectCast(mySvc.MyPackage.packageState, IComPropertyBrowser).SaveState(pbrsKey)   
                        End Using   
                    End Using   
                End Using   
            End If   
        End Sub   
  
        Public Sub LoadSettingsFromStorage()   
            Dim mySvc As MyPackageService = TryCast(GetService(GetType(IVSMDMyPackage)), MyPackageService)   
            Dim package As Package = TryCast(GetService(GetType(Package)), Package)   
            Dim rootKey As RegistryKey = package.UserRegistryRoot   
            Using rootKey   
                Dim pbrsKey As RegistryKey = rootKey.OpenSubKey(Me.[GetType]().Name)   
                If pbrsKey IsNot Nothing Then   
                    Using pbrsKey   
                        If mySvc.MyPackage.MakeCurrentSettingTheDefault() Then   
                            DirectCast(mySvc.MyPackage.packageState, IComPropertyBrowser).SaveState(pbrsKey)   
                        Else   
                            DirectCast(mySvc.MyPackage.packageState, IComPropertyBrowser).LoadState(pbrsKey)   
                        End If   
                    End Using   
                End If   
            End Using   
        End Sub   
    End Class   
End Namespace  
  
```  
  
```c#  
namespace myProfileManagerNameSpace  {  
  
  using System;  
  using System.Runtime.InteropServices;  
  using Microsoft.VisualStudio.Shell;  
  using Microsoft.VisualStudio.Shell.Interop;  
  using Microsoft.Win32;  
  using myPackageNameSpace;  
  
  [Guid("XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX")]  
  internal class MyPackageProfileManager : System.ComponentModel.Component , IProfileManager {  
    internal const int m_supportVer = 8;  
    public void SaveSettingsToXml(IVsSettingsWriter writer) {  
      MyPackageService mySvc = GetService(typeof(MyPackage)) as MyPackageService;  
      if (mySvc != null) {  
        // Information is stored in a StateObject.  
        StateObject myState = mySvc.MyPackage.packageState;  
        writer.WriteSettingString(   
                                  "PbrsAlpha",   
                                  (myState.SortState == SortState.Alphabetical ? "1" : "0"));  
        writer.WriteSettingString(   
                                  "PbrsShowDesc",   
                                  (myState.HelpVisible ? "1" : "0"));  
      }  
    }  
  
    public void LoadSettingsFromXml(IVsSettingsReader reader)  
    {  
  
      int pnMajor, pnMinor, pnBuild;  
      // First check if we are getting data from the correct major version.   
      reader.ReadVersion(pnMajor, pnMinor, pnBuild);  
      if (pnMajor != m_supportVer){  
        reader.ReportError("Unsupported Version");  
      }else{  
        MyPackageService mySvc = GetService(typeof(IVSMDMyPackage)) as MyPackageService;  
        if (mySvc != null){  
          string value;  
          StateObject myState = mySvc.MyPackage.packageState;  
          reader.ReadSettingString("PbrsShowDesc", out value);  
          // Not all values must be present.  
          if (value == null || value == ""){  
              reader.ReportError("Unable to Help Visibility Setting");  
          }else{  
            myState.HelpVisible = !value.Equals("0");  
          }  
          reader.ReadSettingString("PbrsAlpha", out value);  
          // Not all values must be present.  
          if (value == null || value == ""){  
              reader.ReportError("Unable to Retrieve Sort Value");  
          }else{  
            if (!value.Equals("0")){  
              myState.SortState = SortState.Alphabetical;  
            }else{  
              myState.SortState = SortState.Categorized;  
            }  
          }  
        }  
      }  
    }  
  
    public void SaveSettingsToStorage() {  
      MyPackageService mySvc = GetService(typeof(IVSMDMyPackage)) as MyPackageService;  
      Package package = GetService(typeof(Package)) as Package;  
      RegistryKey rootKey = package.UserRegistryRoot;  
  
      if (mySvc.MyPackage.packageState != null) {  
        using (rootKey) {  
          using(RegistryKey pbrsKey = rootKey.CreateSubKey(this.GetType().Name)) {  
            using (pbrsKey) {  
              ((IComPropertyBrowser)mySvc.MyPackage.packageState).SaveState(pbrsKey);  
            }  
          }  
        }  
      }  
    }  
  
    public void LoadSettingsFromStorage() {  
      MyPackageService mySvc = GetService(typeof(IVSMDMyPackage)) as MyPackageService;  
      Package package = GetService(typeof(Package)) as Package;  
      RegistryKey rootKey = package.UserRegistryRoot;  
      using (rootKey) {  
        RegistryKey pbrsKey = rootKey.OpenSubKey(this.GetType().Name);  
        if (pbrsKey != null) {  
          using (pbrsKey) {  
            if (mySvc.MyPackage.MakeCurrentSettingTheDefault()){  
              ((IComPropertyBrowser)mySvc.MyPackage.packageState).SaveState(pbrsKey);  
            }else{  
              ((IComPropertyBrowser)mySvc.MyPackage.packageState).LoadState(pbrsKey);  
            }  
          }  
        }  
      }  
    }  
  }  
}  
```  
  
## Voir aussi  
 <xref:Microsoft.VisualStudio.Shell.IProfileManager>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsWriter>   
 [Exportation de paramètres](../misc/exporting-settings.md)   
 [Prise en charge pour les paramètres utilisateur](../Topic/Support%20for%20User%20Settings.md)