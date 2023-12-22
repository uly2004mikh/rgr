class Schedule:
    def __init__(self):
        self.schedule = {}

    def add_lesson(self, date, lesson):
        if date not in self.schedule:
            self.schedule[date] = []
        self.schedule[date].append(lesson)

    def remove_lesson(self, date, lesson):
        if date in self.schedule and lesson in self.schedule[date]:
            self.schedule[date].remove(lesson)

    def modify_lesson(self, date, old_lesson, new_lesson):
        if date in self.schedule and old_lesson in self.schedule[date]:
            index = self.schedule[date].index(old_lesson)
            self.schedule[date][index] = new_lesson

    def get_lessons(self, date):
        if date in self.schedule:
            return self.schedule[date]
        else:
            return []

# Пример использования
schedule = Schedule()

# Добавление нового занятия в расписание
schedule.add_lesson("2022-01-01", "Математика")
schedule.add_lesson("2022-01-01", "Физика")
schedule.add_lesson("2022-01-02", "История")

# Изменение занятия в расписании
schedule.modify_lesson("2022-01-01", "Математика", "Алгебра")

# Удаление занятия из расписания
schedule.remove_lesson("2022-01-01", "Физика")

# Получение списка занятий на определенную дату
lessons = schedule.get_lessons("2022-01-01")
print(lessons)
