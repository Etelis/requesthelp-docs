---
layout: default
title: Contex Tree
nav_order: 3
---
# Context Tree

```json
{
  "context": {
    "location": {
      "type": "multiclass",
      "values": ["Urban", "Commercial", "Institutional", "Remote"],
      "examples": {
        "Urban": ["City streets", "Shopping malls"],
        "Commercial": ["Shopping centers", "Office buildings", "Retail stores"],
        "Institutional": ["Hospitals", "Schools", "Government buildings"],
        "Remote": ["Isolated roads", "Nature reserves", "Deserted areas"]
      }
    },
    "time": {
      "time_of_day": {
        "type": "multiclass",
        "values": ["Morning", "Afternoon", "Evening", "Night"]
      },
      "day_of_week": {
        "type": "binary",
        "values": ["Weekday", "Weekend"]
      },
      "season": {
        "type": "multiclass",
        "values": ["Spring", "Summer", "Autumn", "Winter"]
      }
    },
    "weather": {
      "weather_conditions": {
        "type": "multiclass",
        "values": ["Sunny", "Rainy", "Snowy", "Windy"]
      }
      "visibility": {
        "type": "multiclass",
        "values": ["Clear", "Foggy", "Low light", "Bright light"]
      }
    },
    "social_context": {
      "crowd_density": {
        "type": "multiclass",
        "values": ["Sparse", "Moderate", "Crowded"]
      },
      "cultural_norms": {
        "type": "binary",
        "values": ["High helping culture", "Low helping culture"]
      },
      "bystander_roles": {
        "type": "multiclass",
        "values": ["Parents with children", "Security personnel", "Tourists"]
      }
      "activity_level": {
        "type": "multiclass",
        "values": ["Low activity", "Moderate activity", "High activity"]
      }
    },
    "robot_features": {
      "familiarity": {
        "type": "binary",
        "values": ["Familiar", "Unfamiliar"]
      },
      "role": {
        "type": "multiclass",
        "values": ["Service", "Security", "Delivery", "Maintenance", "Agriculture", "Surveillance", "Research"]
      },
      "type": {
        "type": "multiclass",
        "values": ["Humanoid", "Zoomorphic", "Industrial"]
      },
      "size": {
        "type": "multiclass",
        "values": ["Small", "Medium", "Large"]
      }
    }
  }
}

```