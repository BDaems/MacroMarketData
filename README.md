# MacroMarketData

kijk naar deze bestandenstructuur:
🧱 Folderstructuur voor Project 1 — Trading Platform
1. /Domain — pure business logica, geen infrastructuur
Entities

Trade.cs

Order.cs

Asset.cs

Indicator.cs

MacroFactor.cs

BorrowData.cs

ShortInterest.cs

ValueObjects

Price.cs

Volume.cs

TimeWindow.cs

TrendSignal.cs

Interfaces

ITradeRepository.cs

IMarketDataProvider.cs

IIndicatorCalculator.cs

IMacroModel.cs

IBorrowDataProvider.cs

Events

TradeExecutedEvent.cs

PriceUpdatedEvent.cs

Services

TradeValidator.cs

RiskModel.cs

MacroNonLinearModel.cs (jouw macro‑consistent model)

2. /Application — use cases, orchestratie, business rules
UseCases

ExecuteTrade.cs

CalculateIndicators.cs

UpdateMacroModel.cs

SyncBorrowData.cs

EvaluateTradeChecklist.cs (jouw praktische checklist)

DTOs

TradeDto.cs

IndicatorResultDto.cs

MacroModelOutputDto.cs

Interfaces

ITradeService.cs

IIndicatorService.cs

IMacroModelService.cs

Mappers

TradeMapper.cs

IndicatorMapper.cs

3. /Infrastructure — data, externe bronnen, implementaties
Persistence

MacroMarketDataDbContext.cs

TradeRepository.cs

BorrowDataRepository.cs

Providers

BinanceMarketDataProvider.cs

FinnhubBorrowDataProvider.cs

EPEXDataIngestor.cs (indien je energie‑data koppelt)

Ingestion

PriceIngestionJob.cs

BorrowDataIngestionJob.cs

MacroFactorIngestionJob.cs

Configuration

DatabaseSettings.cs

ApiKeys.cs (met jouw environment‑variable workflow)

MSensor

ShortInterestScraper.cs

BorrowRateScraper.cs

MSensorParser.cs

4. /Presentation — API, UI, endpoints
API

TradeController.cs

IndicatorController.cs

MacroModelController.cs

BorrowDataController.cs

BlazorDashboard (optioneel)

Pages/

Components/

Services/

5. /Tests — unit tests, integration tests
DomainTests

MacroNonLinearModelTests.cs

RiskModelTests.cs

ApplicationTests

ExecuteTradeTests.cs

IndicatorCalculationTests.cs

InfrastructureTests

TradeRepositoryTests.cs

BorrowDataIngestionTests.cs

IntegrationTests

EndToEndTradeFlowTests.cs
