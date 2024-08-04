# photosynthesisclass Photosynthesis:
    def __init__(self, co2, h2o, sunlight):
        self.co2 = co2
        self.h2o = h2o
        self.sunlight = sunlight
        self.glucose = 0
        self.oxygen = 0

    def perform_photosynthesis(self):
        # Требуется 6 молекул CO2 и 6 молекул H2O для производства 1 молекулы глюкозы и 6 молекул кислорода
        while self.co2 >= 6 and self.h2o >= 6 and self.sunlight > 0:
            self.co2 -= 6
            self.h2o -= 6
            self.sunlight -= 1
            self.glucose += 1
            self.oxygen += 6
        return self.glucose, self.oxygen

    def __str__(self):
        return (f"CO2: {self.co2}, H2O: {self.h2o}, Sunlight: {self.sunlight}, "
                f"Glucose: {self.glucose}, Oxygen: {self.oxygen}")

# Пример использования
co2 = 12   # Количество молекул CO2
h2o = 12   # Количество молекул H2O
sunlight = 2  # Количество единиц световой энергии

photosynthesis_process = Photosynthesis(co2, h2o, sunlight)
print(f"До фотосинтеза: {photosynthesis_process}")

glucose, oxygen = photosynthesis_process.perform_photosynthesis()
print(f"После фотосинтеза: {photosynthesis_process}")
print(f"Произведено глюкозы: {glucose}, Произведено кислорода: {oxygen}")
