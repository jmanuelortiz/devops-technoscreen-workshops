# Crear VMI con Packer 
Para referencia de este workshop visitar el link 
- https://docs.microsoft.com/en-us/azure/virtual-machines/windows/build-image-with-packer

### Herramientas
- Packer
```powershell
choco install packer
```
- Azure PowerShell module 
- Acceso a una cuenta en Azure
  
# Crear un resource Group
```powershell
$rgName = "myResourceGroup"
$location = "East US"
New-AzResourceGroup -Name $rgName -Location $location
```
# Crear credenciales de Azure
```powershell
$sp = New-AzADServicePrincipal -DisplayName "PackerServicePrincipal"
$BSTR = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($sp.Secret)
$plainPassword = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($BSTR)
New-AzRoleAssignment -RoleDefinitionName Contributor -ServicePrincipalName $sp.ApplicationId
```