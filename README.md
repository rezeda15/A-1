# A-1import sqlite3
from datetime import datetime

# Connect to SQLite database (or create it if it doesn't exist)
conn = sqlite3.connect('racket_hits.db')
cursor = conn.cursor()

# Create a table to store racket hit records
cursor.execute('''
CREATE TABLE IF NOT EXISTS hits (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    hit_time TEXT NOT NULL
)
''')
conn.commit()

# Function to add a new racket hit record
def add_hit():
    hit_time = datetime.now().strftime('%Y-%m-%d %H:%M:%S')
    cursor.execute('INSERT
