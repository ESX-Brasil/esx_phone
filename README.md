# esx_phone

### nota
- Todos os scripts que implementam o uso do esx phone devem ser iniciados **após** este script, senão eles serão registrados e nenhuma mensagem será recebida.

## Download & Installation

### Using [fvm](https://github.com/qlaffont/fvm-installer)
```
fvm install --save --folder=esx ESX-Brasil/esx_phone
```

### Using Git
```
cd resources
git clone https://github.com/ESX-Brasil/esx_phone [esx]/esx_phone
```

### Manually
- Download https://github.com/ESX-Brasil/esx_phone/archive/master.zip
- Put it in the `[esx]` directory

- Import `esx_phone.sql` in your database
- Add this in your `server.cfg`:

```
start esx_phone
```

### Adicionar contatos personalizados

Lado do cliente

```lua
RegisterNetEvent('esx_phone:loaded')
AddEventHandler('esx_phone:loaded', function(phoneNumber, contacts)
	local specialContact = {
		name       = 'sociedade nome',
		number     = 'número da sociedade',
		base64Icon = 'insert base 64 icon'
	}

	TriggerEvent('esx_phone:addSpecialContact', specialContact.name, specialContact.number, specialContact.base64Icon)
end)
```

Lado do servidor

```lua
TriggerServerEvent('esx_phone:registerNumber', number, type, sharePos, hasDispatch, hideNumber, hidePosIfAnon)

exemplo

TriggerEvent('esx_phone:registerNumber', 'ambulance', _U('alert_ambulance'), true, true)

os últimos dois booleanos são opcionais
```

# Legal
### License
esx_phone - phone script for fivem

Copyright (C) 2015-2019 Jérémie N'gadi

This program Is free software: you can redistribute it And/Or modify it under the terms Of the GNU General Public License As published by the Free Software Foundation, either version 3 Of the License, Or (at your option) any later version.

This program Is distributed In the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty Of MERCHANTABILITY Or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License For more details.

You should have received a copy Of the GNU General Public License along with this program. If Not, see http://www.gnu.org/licenses/.
