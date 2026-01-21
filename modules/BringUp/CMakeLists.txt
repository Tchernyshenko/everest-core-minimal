if (NOT ftxui_FOUND AND NOT DEFINED ftxui_SOURCE_DIR)
    message(WARNING "Not building BringUp modules because dependency ftxui is not available")
else()
    # ev_add_module(BUDCExternalDerate)       # ⚠️ Не соответствует ни одному модулю в конфигурации
    ev_add_module(BUDisplayMessage)          # ✅ Соответствует display_message в OCPP0 (требование)
    ev_add_module(BUEvseBoardSupport)        # ✅ Соответствует BSPCustom0, ISO15118Custom0
    ev_add_module(BUIsolationMonitor)        # ✅ Соответствует imd (IMDSimulator)
    # ev_add_module(BUOverVoltageMonitor)    # ⚠️ Упомянут в терминалах EvseManager0, но нет модуля в конфигурации
    ev_add_module(BUPowerSupplyDC)           # ✅ Соответствует PowerOutputSupplyDC0
    ev_add_module(BUPowermeter)              # ✅ Соответствует PowerOutputSupplyDC0 (powermeter)
    ev_add_module(BUSystem)                  # ✅ Соответствует System0
    ev_add_module(BUTokenProvider)           # ✅ Соответствует DummyTokenProviderManual0
endif()
