
Select*
From PortfolioProject..CovidDeaths$
Where continent is not Null
order by 3,4


--Select*
--From PortfolioProject..CovidVaccinations$
--order by 3,4


--Select Data that we are going to be using

Select Location, date, total_cases, new_cases, total_deaths, population
From PortfolioProject..CovidDeaths$
order by 1,2

-- Looking at total cases vs total deaths

Select Location, date, total_cases, total_deaths, (total_deaths/total_cases)*100 as DeathPercentage
From PortfolioProject..CovidDeaths$
order by 1,2

--Looking at Total Cases vs Population
--Shows the population that has gotten Covid
Select Location, date, total_cases, population, (total_cases/population)*100 as PercentPopulationInfected
From PortfolioProject..CovidDeaths$
Where location like '%states%'
order by 1,2

--Looking at Countries with Highest Infection Rate compared to Population

Select Location, Population, MAX (total_cases) as  HighestInfectionCount, MAX((total_cases/population))*100
PercentPopulationInfected
From PortfolioProject..CovidDeaths$
--Where location like '%states%'
Group by location, population
order by PercentPopulationInfected desc

--Showing the countries with the highest death count per population
Select Location, MAX (cast (total_deaths as int)) as  TotalDeathCount
From PortfolioProject..CovidDeaths$
--Where location like '%states%'
Where continent is not null
Group by location
Order by TotalDeathCount desc


--LETS BREAK THINGS DOWN BY CONTINENT

 


-- Global Numbers
Select date,Sum (new_cases)as total_cases, SUM(cast(new_deaths as int))as total_deaths, Sum(cast(New_deaths as int))/SUM(New_Cases)*100 as DeathPercentage
From PortfolioProject..CovidDeaths$
-- Where location like '$states%'
where continent is not null
Group By date
order by 1,2


--World Total
Select Sum (new_cases)as total_cases, SUM(cast(new_deaths as int))as total_deaths, Sum(cast(New_deaths as int))/SUM(New_Cases)*100 as DeathPercentage
From PortfolioProject..CovidDeaths$
-- Where location like '$states%'
where continent is not null
--Group By date
order by 1,2


--Joining Data

Select *
From PortfolioProject..CovidDeaths$ dea
Join PortfolioProject..CovidVaccinations$ vac
On dea.location = vac.location
and dea.date = vac.date


 

