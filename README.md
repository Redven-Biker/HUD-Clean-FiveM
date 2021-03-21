Discord : https://discord.gg/C3aN2bBVbB



esx_status\client\main.lua replace line 71 by

TriggerEvent('hud_clean:updateBasics', GetStatusData(true))


esx_basicneeds\client\main.lua replace line 40 by


AddEventHandler('esx_status:loaded', function(status)

	TriggerEvent('esx_status:registerStatus', 'hunger', 1000000, '#FFFF00', -- amarelo
	--TriggerEvent('esx_status:registerStatus', 'hunger', 1000000, '#CFAD0F', -- GOLD
		function(status)
			return false -- Change to true to show hunger bar | false to hide hunger bar
		end, function(status)
			status.remove(100)
		end
	)

	TriggerEvent('esx_status:registerStatus', 'thirst', 1000000, '#0099FF', -- azul
	--TriggerEvent('esx_status:registerStatus', 'thirst', 1000000, '#0C98F1', -- CYAN
		function(status)
			return false -- Change to true to show thirst bar | false to hide thirst bar
		end, function(status)
			status.remove(75)
		end
	)
