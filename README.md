# k8s-27-04-2021

## Instrukcja instalacji `az cli` na maszynie laboratoryjnej

1. Zaloguj się SSH na maszynę laboratoryjną
1. Wykonaj komendę: `curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash` (instalacja zajmie około 2 minut)
1. Podaj hasło, którego używałaś/-eś podczas logowania do maszyny
1. Wykonaj komendę `az version` i sprawdź czy otrzymałeś output podobny do:

   ```bash
   $ az version

   {
     "azure-cli": "2.22.1",
     "azure-cli-core": "2.22.1",
     "azure-cli-telemetry": "1.0.6",
     "extensions": {}
   }
   ```

1. Wykonaj komendę `az login --use-device-code`. Przeczytaj dokładnie wypisany przez komendę output.
1. W przeglądarce na swojej własnej maszynie przejdź na adres: https://microsoft.com/devicelogin.
1. Skopiuj kod wypisany w output ostatniej komendy. W wyświetlonym na stronie formularzu wklej skopiowany kod.
1. Wybierz konto w domenie `@chmurowiskolab.onmicrosoft.com`
1. Wróć do terminala w którym jesteś zalogowany do maszyny laboratoryjnej. Sprawdź czy otrzymałeś output podobny do poniższego (powinien pojawić się w ciągu 10 sekund).

   ```json
    $ az login --use-device-code

    To sign in, use a web browser to open the page https://microsoft.com/devicelogin and enter the code D4PSWWY76 to authenticate.
    The following tenants don't contain accessible subscriptions. Use 'az login --allow-no-subscriptions' to have tenant level access.
    [
      {
        "cloudName": "AzureCloud",
        "homeTenantId": "11112222-3333-4444-5555-666677778888",
        "id": "11112222-3333-4444-5555-666677778888",
        "isDefault": true,
        "managedByTenants": [],
        "name": "MPN",
        "state": "Enabled",
        "tenantId": "11112222-3333-4444-5555-666677778888",
        "user": {
          "name": "maciej.borowy@chmurowisko.pl",
          "type": "user"
        }
      }
    ]
   ```

1. Zostałaś/eś poprawnie zalogowany do Azure z poziomu `az cli`
1. Wykonaj komendę `az aks list` i sprawdź czy w wpisanym output widzisz klaster AKS z utworzoną przez siebie nazwą:

   ```bash
    $ az aks list

    [
      {
        "aadProfile": null,
        ...
        "name": "<TWOJA_NAZWA_KLASTRA>",
        ...
        "resourceGroup": "<NAZWA_TWOJEJ_RESOURCE_GROUP>",
        ...
      }
    ]
   ```
