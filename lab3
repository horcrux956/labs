
items = {
    'в': {'size': 3, 'points': 25},
    'п': {'size': 2, 'points': 15},
    'б': {'size': 2, 'points': 15},
    'а': {'size': 2, 'points': 20},
    'и': {'size': 1, 'points': 5},
    'н': {'size': 1, 'points': 15},
    'т': {'size': 3, 'points': 20},
    'о': {'size': 1, 'points': 25},
    'ф': {'size': 1, 'points': 15},
    'д': {'size': 1, 'points': 10},
    'к': {'size': 2, 'points': 20},
    'р': {'size': 2, 'points': 20}
}

available_items = ['в', 'п', 'б', 'а', 'и', 'н', 'т', 'о', 'ф', 'д', 'к', 'р']

backpack = [[' ' for i in range(4)] for j in range(2)]

survival_points = -85

while available_items:
    max_points = 0
    best_item = None
    best_row = None
    best_index = None
    
    for item in available_items:
        item_size = items[item]['size']
        for row in range(len(backpack)):
            for i in range(4 - item_size + 1):
                if ' ' not in backpack[row][i:i+item_size]:
                    continue
                points = items[item]['points']
                for j in range(i, i+item_size):
                    if backpack[row][j] != ' ':
                        points -= items[backpack[row][j]]['points']
                if points > max_points:
                    max_points = points
                    best_item = item
                    best_row = row
                    best_index = i
    
    if best_item is None:
        break
    
    item_size = items[best_item]['size']
    for i in range(item_size):
        backpack[best_row][best_index+i] = best_item
    available_items.remove(best_item)
    survival_points += max_points

for row in backpack:
    print(row)
print('Итоговые очки выживания:', max(0, survival_points))
