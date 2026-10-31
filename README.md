# ==========================================
# Project: ApexCraft
# Description:
# The highest point of creativity and engineering,
# dedicated to building impactful applications.
# ==========================================


# ---------- main.py ----------
"""
Main entry point for ApexCraft.
"""

from core.creativity import CreativeEngine
from core.engineering import EngineeringCore
from core.impact import ImpactEngine


def run():
    print("🚀 ApexCraft Initialized")
    print("🎨 Creativity | ⚙️ Engineering | 💥 Impact\n")

    creativity = CreativeEngine()
    engineering = EngineeringCore()
    impact = ImpactEngine()

    ideas = ["automation", "analytics", "productivity"]
    data = [10, 20, 30, 40]

    print("💡 Creative Concepts:")
    print(creativity.generate(ideas))

    print("\n⚙️ Engineered Output:")
    print(engineering.process(data))

    print("\n💥 Application Impact:")
    print(impact.measure(data))


if __name__ == "__main__":
    run()


# ---------- core/creativity.py ----------
"""
Creative idea generation utilities.
"""


class CreativeEngine:
    """Transforms concepts into application ideas."""

    def generate(self, ideas):
        """Generate application concepts from raw ideas."""
        return [f"{idea}_app" for idea in ideas]

    def combine(self, *ideas):
        """Combine multiple concepts into one idea."""
        return " + ".join(ideas)


# ---------- core/engineering.py ----------
"""
Engineering and application processing utilities.
"""


class EngineeringCore:
    """Provides structured application processing."""

    def process(self, values):
        """Process data through a reliable pipeline."""
        return [
            {
                "input": value,
                "output": value * 2,
                "status": "processed"
            }
            for value in values
        ]

    def validate(self, values):
        """Validate application input."""
        return all(isinstance(value, (int, float)) for value in values)


# ---------- core/impact.py ----------
"""
Impact measurement utilities.
"""


class ImpactEngine:
    """Measures the potential impact of application data."""

    def measure(self, values):
        """Calculate a simple impact metric."""
        if not values:
            return 0

        return round(sum(values) / len(values), 2)

    def amplify(self, score, factor=1.5):
        """Project an amplified impact score."""
        return round(score * factor, 2)


# ---------- tests/test_creativity.py ----------
from core.creativity import CreativeEngine


def test_generate():
    engine = CreativeEngine()
    assert "ai_app" in engine.generate(["ai"])


def test_combine():
    engine = CreativeEngine()
    assert engine.combine("AI", "Cloud") == "AI + Cloud"


# ---------- tests/test_engineering.py ----------
from core.engineering import EngineeringCore


def test_process():
    engine = EngineeringCore()
    result = engine.process([2])
    assert result[0]["output"] == 4
    assert result[0]["status"] == "processed"


def test_validate():
    engine = EngineeringCore()
    assert engine.validate([1, 2, 3]) is True


# ---------- tests/test_impact.py ----------
from core.impact import ImpactEngine


def test_measure():
    engine = ImpactEngine()
    assert engine.measure([10, 20, 30]) == 20


def test_amplify():
    engine = ImpactEngine()
    assert engine.amplify(100) == 150
